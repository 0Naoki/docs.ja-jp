---
title: ASP.NET 互換性
ms.date: 03/30/2017
ms.assetid: c8b51f1e-c096-4c42-ad99-0519887bbbc5
ms.openlocfilehash: e9566c24756afef98c8594c8d7b542bd2ad1e5b5
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2019
ms.locfileid: "70045172"
---
# <a name="aspnet-compatibility"></a>ASP.NET 互換性

このサンプルでは、Windows Communication Foundation (WCF) で ASP.NET 互換モードを有効にする方法を示します。 ASP.NET 互換モードで実行されているサービスは、ASP.NET アプリケーションパイプラインに完全に参加し、ファイル/URL 認証、セッション状態、 <xref:System.Web.HttpContext>クラスなどの ASP.NET 機能を利用できます。 <xref:System.Web.HttpContext>クラスを使用すると、cookie、セッション、およびその他の ASP.NET 機能にアクセスできます。 このモードでは、バインディングは HTTP トランスポートを使用し、サービス自体は IIS でホストされる必要があります。

このサンプルでは、クライアントはコンソール アプリケーション (.exe) で、サービスはインターネット インフォメーション サービス (IIS) によってホストされています。

> [!NOTE]
> このサンプルのセットアップ手順とビルド手順については、このトピックの最後を参照してください。

このサンプルを実行するには、[!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] アプリケーション プールが必要です。 新しいアプリケーション プールの作成または既定のアプリケーション プールの変更を行うには、次の手順に従います。

1. **[コントロール パネル]** を開きます。  **[システムとセキュリティ]** 見出しの下にある **[管理ツール]** アプレットを開きます。 **インターネットインフォメーションサービス (IIS) マネージャー**アプレットを開きます。

2. **[接続]** ウィンドウで treeview を展開します。 **[アプリケーションプール]** ノードを選択します。

3. 使用する既定のアプリケーション プールを設定する[!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)](既存のサイトと非互換性の問題が発生する可能性があります、) を右クリックし、 **DefaultAppPool**リスト項目と選択**基本設定しています...** . **.Net Framework バージョン**のプルダウンを **.net framework v v4.0.30128** (またはそれ以降) に設定します。

4. 使用する新しいアプリケーション プールを作成する[!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)](互換性を保持する他のアプリケーション)、右クリックし、**アプリケーション プール**ノード**アプリケーション プールの追加しています...** . 新しいアプリケーションプールにという名前を設定し、 **[.Net Framework バージョン]** プルダウンを **[.net framework v v4.0.30128]** (またはそれ以降) に設定します。 下、セットアップを実行する手順は、後に右クリックし、 **ServiceModelSamples**アプリケーションと選択**アプリケーションの管理**、**詳細設定しています...** . **アプリケーションプール**を新しいアプリケーションプールに設定します。

> [!IMPORTANT]
> サンプルは、既にコンピューターにインストールされている場合があります。 続行する前に、次の (既定の) ディレクトリを確認してください。
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> このディレクトリが存在しない場合は、 [Windows Communication Foundation (wcf) および Windows Workflow Foundation (WF) のサンプルの .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780)にアクセスして、すべての[!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (wcf) とサンプルをダウンロードしてください。 このサンプルは、次のディレクトリに格納されます。
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebHost\ASPNetCompatibility`

このサンプルは、電卓サービスを実装する[はじめに](../../../../docs/framework/wcf/samples/getting-started-sample.md)に基づいています。 `ICalculator` コントラクトは、一連の算術演算を実行して実行結果を保持できるように `ICalculatorSession` コントラクトに変更されました。

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface ICalculatorSession
{
    [OperationContract]
    void Clear();
    [OperationContract]
    void AddTo(double n);
    [OperationContract]
    void SubtractFrom(double n);
    [OperationContract]
    void MultiplyBy(double n);
    [OperationContract]
    void DivideBy(double n);
    [OperationContract]
    double Result();
}
```

サービスはこの機能を使用して、複数のサービス操作が呼び出されて計算を実行する際に、各クライアントの状態を保持します。 クライアントは `Result` を呼び出して現在の結果を取得したり、`Clear` を呼び出してその結果をクリアし、0 にすることができます。

サービスは、ASP.NET セッションを使用して、各クライアントセッションの結果を格納します。 これにより、サービスは、サービスへの複数の呼び出しによる各クライアントの実行結果を保持できます。

> [!NOTE]
> ASP.NET セッション状態と WCF セッションは、非常に異なるものです。 WCF セッションの詳細については、「[セッション](../../../../docs/framework/wcf/samples/session.md)」を参照してください。

このサービスは、ASP.NET セッション状態に対してより深い依存関係を持ち、ASP.NET 互換モードが正常に機能することを必要とします。 これらの要件は、`AspNetCompatibilityRequirements` 属性を適用することにより宣言によって表されます。

```csharp
[AspNetCompatibilityRequirements(RequirementsMode =
                       AspNetCompatibilityRequirementsMode.Required)]
public class CalculatorService : ICalculatorSession
{
    double Result
    {  // store result in AspNet Session
       get {
          if (HttpContext.Current.Session["Result"] != null)
             return (double)HttpContext.Current.Session["Result"];
          return 0.0D;
       }
       set
       {
          HttpContext.Current.Session["Result"] = value;
       }
    }
    public void Clear()
    {
        Result = 0.0D;
    }
    public void AddTo(double n)
    {
        Result += n;
    }
    public void SubtractFrom(double n)
    {
        Result -= n;
    }
    public void MultiplyBy(double n)
    {
        Result *= n;
    }
    public void DivideBy(double n)
    {
        Result /= n;
    }
    public double Result()
    {
        return Result;
    }
}
```

このサンプルを実行すると、操作要求および応答がクライアントのコンソール ウィンドウに表示されます。 クライアントをシャットダウンするには、クライアント ウィンドウで Enter キーを押します。

```console
0, + 100, - 50, * 17.65, / 2 = 441.25
Press <ENTER> to terminate client.
```

### <a name="to-set-up-build-and-run-the-sample"></a>サンプルをセットアップ、ビルド、および実行するには

1. [Windows Communication Foundation サンプルの1回限りのセットアップ手順](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)を実行していることを確認してください。

2. ソリューションの C# 版または Visual Basic .NET 版をビルドするには、「 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)」の手順に従います。

3. ソリューションがビルドされたら、Setup.exe を実行して IIS 7.0 で ServiceModelSamples アプリケーションを設定します。 これで、ServiceModelSamples ディレクトリが IIS 7.0 アプリケーションとして表示されます。

4. サンプルを単一コンピューター構成または複数コンピューター構成で実行するには、「 [Windows Communication Foundation サンプルの実行](../../../../docs/framework/wcf/samples/running-the-samples.md)」の手順に従います。

## <a name="see-also"></a>関連項目

- [AppFabric のホスティングと永続化のサンプル](https://go.microsoft.com/fwlink/?LinkId=193961)
