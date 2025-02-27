---
title: '方法: インストールされている .NET Framework バージョンを確認する'
ms.date: 04/18/2019
dev_langs:
- csharp
- vb
ms.custom: updateeachrelease
helpviewer_keywords:
- versions, determining for .NET Framework
- .NET Framework, determining version
ms.assetid: 40a67826-e4df-4f59-a651-d9eb0fdc755d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: abfa42be4b8c759da3fb34a2204058143e39689c
ms.sourcegitcommit: 7bfe1682d9368cf88d43e895d1e80ba2d88c3a99
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2019
ms.locfileid: "71956669"
---
# <a name="how-to-determine-which-net-framework-versions-are-installed"></a>方法: インストールされている .NET Framework バージョンを確認する

ユーザーはコンピューターに複数のバージョンの .NET Framework を[インストール](https://docs.microsoft.com/dotnet/framework/install)して実行できます。 アプリを開発または配置する場合、どのバージョンの .NET Framework がユーザーのコンピューターにインストールされているかを確認しなければならない場合があります。

.NET Framework は、個別にバージョン管理される 2 つの主要コンポーネントで構成されています。

- アプリに機能を提供する型やリソースのコレクションである一連のアセンブリ。 .NET Framework とアセンブリは同じバージョン番号を共有します。

- アプリのコードを管理および実行する共通言語ランタイム (CLR)。 CLR は独自のバージョン番号で識別されます (「[バージョンおよび依存関係](versions-and-dependencies.md)」を参照してください)。

> [!NOTE]
> 新しい各バージョンの .NET Framework には、1 つ前のバージョンの機能が含まれると共に、新機能が追加されています。 同じコンピューターに .NET Framework の複数のバージョンを同時に読み込むことができます。これは、以前のバージョンをアンインストールせずに、.NET Framework をインストールできることを意味します。 一般に、以前の .NET Framework のバージョンはアンインストールしないでください。使用するアプリケーションが特定のバージョンに依存しており、そのバージョンが削除されると破損してしまう可能性があります。
>
> .NET Framework のバージョンと CLR のバージョンの間には違いがあります。
>
> - .NET Framework は、.NET Framework のクラス ライブラリを構成するアセンブリのセットに基づいてバージョン管理されています。 たとえば、.NET Framework のバージョンには、4.5、4.6.1、および 4.7.2 が含まれます。
>- CLR は、.NET Framework アプリケーションが実行されているランタイムに基づいてバージョン管理されています。 1 つの CLR バージョンは、通常複数の NET Framework バージョンをサポートしています。 たとえば、CLR バージョン 4.0.30319.*xxxxx* (ここでの *xxxxx* は 42000 より小さい) は .NET Framework バージョン 4 から 4.5.2 をサポートしており、CLR バージョン 4.0.30319.42000 では .NET Framework 4.6 以降をサポートします。
>
> バージョンの詳細については、「[.NET Framework のバージョンおよび依存関係](versions-and-dependencies.md)」を参照してください。

コンピューターにインストールされている .NET Framework のバージョンの一覧を取得するには、レジストリにアクセスします。 レジストリを確認するには、レジストリ エディタを使用するか、次に従ってコードで照会します。

- .NET Framework の新しいバージョンを探す (4.5 以降):
  - [レジストリ エディターを使用し .NET Framework のバージョンを探す](#net_b)
  - [コードを使用し .NET Framework のバージョンのレジストリを照会する](#net_d)
  - [PowerShell を使用し .NET Framework のバージョンのレジストリを照会する](#ps_a)
- .NET Framework の古いバージョンを探す (1 から 4):
  - [レジストリ エディターを使用し .NET Framework のバージョンを探す](#net_a)
  - [コードを使用し .NET Framework のバージョンのレジストリを照会する](#net_c)

コンピューターにインストールされている CLR のバージョンの一覧を取得するには、次のツールまたはコードを使用します。

- [Clrver ツールを使用する](#clr_a)
- [コードを使用して Environment クラスを照会する](#clr_b)

.NET Framework の各バージョン用にインストールされている更新プログラムの検出については、「[方法:インストールされている .NET Framework の更新プログラムを確認する](how-to-determine-which-net-framework-updates-are-installed.md)」を参照してください。

## <a name="find-newer-net-framework-versions-45-and-later"></a>.NET Framework の新しいバージョンを探す (4.5 以降)

<a name="net_b"></a>

### <a name="find-net-framework-versions-45-and-later-in-the-registry"></a>レジストリで .NET Framework バージョン 4.5 以降を探す

1. **スタート** メニューの **[ファイル名を指定して実行]** を選択し、「*regedit*」と入力し、 **[OK]** を選択します。

     regedit を実行するには、管理特権が必要です。

2. レジストリ エディターで、次のサブキーを開きます。**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** **Full** サブキーが存在しない場合は、.NET Framework 4.5 以降はインストールされていません。

    > [!NOTE]
    > レジストリの **NET Framework セットアップ** フォルダーの先頭はピリオドでは "*ありません*"。

3. **Release** という DWORD のエントリを探します。 それがある場合、.NET Framework 4.5 以降のバージョンがインストールされています。 その値は、.NET Framework の特定のバージョンのリリース キーです。 たとえば、次の図では、**Release** エントリの値は *378389* で、これは .NET Framework 4.5 のリリース キーです。

     ![.NET Framework 4.5 のレジストリ エントリ](./media/clr-installdir.png ".NET Framework 4.5 のレジストリ エントリ")

次の表は、.NET Framework 4.5 以降のバージョンに対する個々のオペレーティング システムでの **Release** DWORD 値の一覧です。

[!INCLUDE[Release key values note](~/includes/version-keys-note.md)]

<a name="version_table"></a>

|.NET Framework のバージョン|Release DWORD の値|
|--------------------------------|-------------|
|.NET Framework 4.5|すべての Windows オペレーティング システム:378389|
|.NET Framework 4.5.1|Windows 8.1 および Windows Server 2012 R2:378675<br />他のすべての Windows オペレーティング システム:378758|
|.NET Framework 4.5.2|すべての Windows オペレーティング システム:379893|
|.NET Framework 4.6|Windows 10:393295<br />他のすべての Windows オペレーティング システム:393297|
|.NET Framework 4.6.1|Windows 10 November Update システム:394254<br />他のすべての Windows オペレーティング システム (Windows 10 を含む):394271|
|.NET Framework 4.6.2|Windows 10 Anniversary Update および Windows Server 2016 の場合:394802<br />他のすべての Windows オペレーティング システム (他の Windows 10 オペレーティング システムを含む):394806|
|.NET Framework 4.7|Windows 10 Creators Update:460798<br />他のすべての Windows オペレーティング システム (他の Windows 10 オペレーティング システムを含む):460805|
|.NET Framework 4.7.1|Windows 10 Fall Creators Update および Windows Server バージョン 1709:461308<br/>他のすべての Windows オペレーティング システム (他の Windows 10 オペレーティング システムを含む):461310|
|.NET Framework 4.7.2|Windows 10 April 2018 Update および Windows Server バージョン 1803:461808<br/>Windows 10 April 2018 Update および Windows Server バージョン 1803 以外のすべての Windows オペレーティング システム:461814|
|.NET Framework 4.8|Windows 10 May 2019 Update: 528040<br/>他のすべての Windows オペレーティング システム (他の Windows 10 オペレーティング システムを含む): 528049|

これらの値は次のように使用できます。

- 特定のバージョンの .NET Framework が特定のバージョンの Windows オペレーティング システムにインストールされているかどうかを判断するには、**Release** DWORD 値が表に記載されている値と "*同じ*" であることを確認します。 たとえば、.NET Framework 4.6 が Windows 10 システム上に存在するかどうかを判断するには、**Release** 値が 393295 と "*同じ*" であることを確認します。

- .NET Framework の最小バージョンが存在するかどうかを判断するには、そのバージョン用の小さい **RELEASE** DWORD 値を使用します。 たとえば、アプリケーションが .NET Framework 4.6 以降のバージョンで実行されている場合、**RELEASE** DWORD 値が 393295 "*以上*" であることを確認します。 各 .NET Framework バージョンの最小 **RELEASE** DWORD 値のみが記載された表については、「[The minimum values of the Release DWORD for .NET Framework 4.5 and later versions (.NET Framework 4.5 以降のバージョン用の Release DWORD の最小値)](minimum-release-dword.md)」を参照してください。

- 複数のバージョンを確認するには、まず、値が最新の .NET Framework バージョン用の小さい DWORD 値 "*以上*" であることを確認してから、その値と、それよりも以前のバージョン用の小さい DWORD 値を順番に比較します。 たとえば、アプリケーションに .NET Framework 4.7 以降が必要で、存在する .NET Framework の特定のバージョンを確認する場合は、461808 (.NET Framework 4.7.2 用の小さい DWORD 値) "*以上*" の **RELEASE** DWORD 値であることの確認から始めます。 次に、**RELEASE** DWORD 値と、以降の各 .NET Framework バージョン用の小さい値と比較します。 各 .NET Framework バージョンの最小 **RELEASE** DWORD 値のみが記載された表については、「[The minimum values of the Release DWORD for .NET Framework 4.5 and later versions (.NET Framework 4.5 以降のバージョン用の Release DWORD の最小値)](minimum-release-dword.md)」を参照してください。

<a name="net_d"></a>

### <a name="find-net-framework-versions-45-and-later-with-code"></a>コードで .NET Framework バージョン 4.5 以降を探す

1. <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> メソッドと <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType> メソッドを使用し、Windows レジストリの **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** サブキーにアクセスします。

    **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** サブキーに **Release** DWORD があるということは、コンピューターに .NET Framework 4.5 以降のバージョンがインストールされていることを意味します。

2. **Release** エントリの値を確認して、インストールされているバージョンを判断します。 上位互換性があるかを確認するには、[.NET Framework のバージョンの表](#version_table)で示されている値以上の値があることを確認します。

次の例では、レジストリから **Release** の値を確認し、インストールされている .NET Framework 4.5 以降のバージョンを探しています。

[!code-csharp[ListVersions#5](../../../samples/snippets/csharp/framework/migration-guide/versions-installed3.cs)]
[!code-vb[ListVersions#5](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed3.vb)]

この例では、バージョンのチェックで推奨されている方法に従います。

- **Release** エントリの値が、既知のリリース キー値*以上*かどうかを確認しています。

- 最新バージョンから最も古いバージョンの順にチェックします。

<a name="ps_a"></a>

### <a name="check-for-a-minimum-required-net-framework-version-45-and-later-with-powershell"></a>PowerShell を使用して最低限必要な .NET Framework のバージョン (4.5 以降) を確認する

- PowerShell コマンドを使用し、**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** サブキーから **Release** エントリの値を確認します。

次の例では、**Release** エントリの値を確認して、.NET Framework 4.6.2 以降がインストールされているかどうかを判断しています。 このコードでは、インストールされていない場合は、`True` が返され、されている場合は `False` が返されます。

```PowerShell
(Get-ItemProperty "HKLM:SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full").Release -ge 394802
```

さまざまな必要最低限の .NET Framework バージョンを確認するには、これらの例の *394802* を [.NET Framework のバージョンの表](#version_table)の **Release** 値と置き換えます。

## <a name="find-older-net-framework-versions-182114"></a>.NET Framework の古いバージョンを探す (1 から 4)

<a name="net_a"></a>

### <a name="find-net-framework-versions-182114-in-the-registry"></a>レジストリで .NET Framework バージョン 1 から 4 を探す

1. **スタート** メニューの **[ファイル名を指定して実行]** を選択し、「*regedit*」と入力し、 **[OK]** を選択します。

    regedit を実行するには、管理特権が必要です。

2. レジストリ エディターで、次のサブキーを開きます。**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP**:

    - .NET Framework バージョン 1.1 から 3.5 では、インストールされている各バージョンは **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP** サブキーの下にサブキーとして列挙されます。 たとえば、**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.5** です。 バージョン番号は、バージョン サブキーの **Version** エントリに値として格納されています。

    - .NET Framework 4 では、**Version** エントリは、**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Client** サブキー、**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Full** サブキーまたは両サブキーの下にあります。

    > [!NOTE]
    > レジストリの **NET Framework セットアップ** フォルダーの先頭はピリオドではありません。

    次の図では、.NET Framework 3.5 のサブキーとその **Version** エントリを示しています。

    ![.NET Framework 3.5 のレジストリ エントリ。](./media/net-4-and-earlier.png ".NET Framework 3.5 以前のバージョン")

<a name="net_c"></a>

### <a name="find-net-framework-versions-182114-with-code"></a>コードで .NET Framework バージョン 1 から 4 を探す

- <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> クラスを使用して、Windows レジストリの **HKEY_LOCAL_MACHINE\Software\Microsoft\NET Framework Setup\NDP** サブキーにアクセスします。

次の例では、インストールされている .NET Framework のバージョン 1 から 4 が検索されています。

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed1.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed1.vb)]

## <a name="find-clr-versions"></a>CLR のバージョンを探す

<a name="clr_a"></a>

### <a name="find-the-current-clr-version-with-clrverexe"></a>Clrver.exe を使用して現在の CLR のバージョンを調べる

[CLR バージョン ツール (Clrver.exe)](../tools/clrver-exe-clr-version-tool.md) を使用して、コンピューターにインストールされている CLR のバージョンを確認します。

- [Visual Studio 用開発者コマンド プロンプト](https://docs.microsoft.com/dotnet/framework/tools/developer-command-prompt-for-vs)で「`clrver`」と入力します。

    出力例:

    ```console
    Versions installed on the machine:
    v2.0.50727
    v4.0.30319
    ```

<a name="clr_b"></a>

### <a name="find-the-current-clr-version-with-the-environment-class"></a>Environment クラスを使用して現在の CLR のバージョンを調べる

> [!IMPORTANT]
> .NET Framework 4.5 以降のバージョンでは、CLR のバージョンの検出に <xref:System.Environment.Version%2A?displayProperty=nameWithType> プロパティを使用しないでください。 代わりに、「[コードで .NET Framework バージョン 4.5 以降を探す](#net_d)」の説明に従い、レジストリを照会します。

1. <xref:System.Environment.Version?displayProperty=nameWithType> プロパティを照会し、<xref:System.Version> オブジェクトを取得します。

    返された `System.Version` オブジェクトは、現在コードを実行しているランタイムのバージョンを示しています。 コンピューターにインストールされている可能性のある、アセンブリのバージョンやランタイムのその他のバージョンは返されません。

    .NET Framework バージョン 4、4.5、4.5.1、4.5.2 の場合は、返される <xref:System.Version> オブジェクトの文字列表現は 4.0.30319.*xxxxx* という形式です。ここでの *xxxxx* は 42000 より小さいです。 .NET Framework 4.6 以降のバージョンの場合は、4.0.30319.42000 という形式です。

2. `Version` オブジェクトを取得したら、次のように照会します。

   - メジャー リリース識別子 (たとえば、バージョン 4.0 の場合の *4*) には、<xref:System.Version.Major%2A?displayProperty=nameWithType> プロパティを使用します。

   - マイナー リリース識別子 (たとえば、バージョン 4.0 の場合の *0*) には、<xref:System.Version.Minor%2A?displayProperty=nameWithType> プロパティを使用します。

   - バージョンの完全な文字列 (たとえば、*4.0.30319.18010*) には、<xref:System.Version.ToString%2A?displayProperty=nameWithType> メソッドを使用します。 このメソッドでは、コードを実行しているランタイムのバージョンを示す値が 1 つ返されます。 コンピューターにインストールされている可能性のあるアセンブリ バージョンやその他のランタイム バージョンは返されません。

次の例では、<xref:System.Environment.Version%2A?displayProperty=nameWithType> プロパティを使用して CLR バージョンの情報を取得しています。

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed2.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed2.vb)]

## <a name="see-also"></a>関連項目

- [方法: インストールされている .NET Framework の更新プログラムを確認する](how-to-determine-which-net-framework-updates-are-installed.md)
- [開発者向けの .NET Framework のインストール](../install/guide-for-developers.md)
- [.NET Framework のバージョンおよび依存関係](versions-and-dependencies.md)
