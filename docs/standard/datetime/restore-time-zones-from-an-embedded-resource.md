---
title: '方法: 埋め込みリソースからタイム ゾーンを復元'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], deserializing
- time zones [.NET Framework], restoring
ms.assetid: 6b7b4de9-da07-47e3-8f4c-823f81798ee7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 99d38b336b5e655dd1c96682eec90c5fbe8469d6
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2018
ms.locfileid: "46699132"
---
# <a name="how-to-restore-time-zones-from-an-embedded-resource"></a>方法: 埋め込みリソースからタイム ゾーンを復元

このトピックでは、リソース ファイルに保存されているタイム ゾーンを復元する方法について説明します。 情報およびタイム ゾーンを保存する方法の手順では、次を参照してください。[方法: 埋め込みリソースにタイム ゾーンを保存](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)します。

### <a name="to-deserialize-a-timezoneinfo-object-from-an-embedded-resource"></a>埋め込みリソースから TimeZoneInfo オブジェクトを逆シリアル化するには

1. 取得するタイム ゾーンでない場合、カスタム タイム ゾーンを使用してインスタンス化することをお試しください。、<xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A>メソッド。

2. インスタンスを作成、<xref:System.Resources.ResourceManager>リソース ファイルを含むアセンブリへの参照と埋め込みリソース ファイルの完全修飾名を渡すことによってオブジェクト。

   使用して、埋め込みリソース ファイルの完全修飾名を特定できない場合、 [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md)アセンブリのマニフェストを確認します。 `.mresource`エントリは、リソースを識別します。 リソースの完全修飾名は、例では、`SerializeTimeZoneData.SerializedTimeZones`します。

   呼び出してへの参照を取得するには、リソース ファイルは、タイム ゾーンのインスタンス化コードを含む同じアセンブリに埋め込まれている場合、 `static` (`Shared` Visual Basic で)<xref:System.Reflection.Assembly.GetExecutingAssembly%2A>メソッド。

3. 場合に呼び出し、<xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A>メソッドが失敗した、またはカスタムのタイム ゾーンをインスタンス化する場合は、呼び出すことによって、シリアル化されたタイム ゾーンを格納する文字列を取得、<xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType>メソッド。

4. 呼び出すことによって、タイム ゾーン データを逆シリアル化、<xref:System.TimeZoneInfo.FromSerializedString%2A>メソッド。

## <a name="example"></a>例

次の例では、逆シリアル化、 <xref:System.TimeZoneInfo> embedded .NET XML リソース ファイルに格納されているオブジェクト。

[!code-csharp[TimeZone2.Serialization#3](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#3)]
[!code-vb[TimeZone2.Serialization#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#3)]

このコードは、ことを確認する例外処理を示しています、<xref:System.TimeZoneInfo>アプリケーションで必要なオブジェクトが存在します。 インスタンスを作成するときはまず、<xref:System.TimeZoneInfo>オブジェクトを使用して、レジストリから取得して、<xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A>メソッド。 タイム ゾーンをインスタンス化できない場合は、埋め込みリソース ファイルから取得します。

ため、カスタムのタイム ゾーンのデータ (を使用してインスタンスのタイム ゾーン、<xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>メソッド) が格納されていないレジストリで、コードを呼び出すことはできません、 <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> Palmer、南極大陸のタイム ゾーンをインスタンス化します。 呼び出す前に、タイム ゾーンのデータを含む文字列を取得する埋め込みリソース ファイルをすぐに確認、代わりに、<xref:System.TimeZoneInfo.FromSerializedString%2A>メソッド。

## <a name="compiling-the-code"></a>コードのコンパイル

この例で必要な要素は次のとおりです。

* System.Windows.Forms.dll、System.Core.dll への参照をプロジェクトに追加します。

* 次の名前空間は、インポートします。

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a>関連項目

* [日付、時刻、およびタイム ゾーン](../../../docs/standard/datetime/index.md)
* [タイム ゾーンの概要](../../../docs/standard/datetime/time-zone-overview.md)
* [方法: 埋め込みリソースにタイム ゾーンを保存する](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
