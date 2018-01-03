---
title: "方法: ラッパを手動で作成する"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: wrappers, creating manually
ms.assetid: cc2a70d8-6a58-4071-a8cf-ce28c018c09b
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c6826a9b214e7507c63752a8a990116b88dda09d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-wrappers-manually"></a>方法: ラッパを手動で作成する
マネージ ソース コード内で COM の型を手動で宣言することにした場合、まず既存のインターフェイス定義言語 (IDL: Interface Definition Language) ファイルまたはタイプ ライブラリを用意することをお勧めします。 IDL ファイルがないか、またはタイプ ライブラリ ファイルを生成できない場合には、マネージ宣言を作成してその結果のアセンブリをタイプ ライブラリにエクスポートすることで、COM の型をシミュレートできます。  
  
### <a name="to-simulate-com-types-from-managed-source"></a>マネージ ソースから COM の型をシミュレートするには  
  
1.  共通言語仕様 (CLS: Common Language Specification) に準拠した言語を使用して型を宣言してからファイルをコンパイルします。  
  
2.  [タイプ ライブラリ エクスポーター (Tlbexp.exe)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) を使用して、その型を含むアセンブリをエクスポートします。  
  
3.  エクスポートした COM タイプ ライブラリを、COM 指向のマネージ型を宣言するための基礎として使用します。  
  
### <a name="to-create-a-runtime-callable-wrapper-rcw"></a>ランタイム呼び出し可能ラッパー (RCW: Runtime Callable Wrapper) を作成するには  
  
1.  IDL ファイルまたはタイプ ライブラリ ファイルがあることを前提として、カスタム RCW に含めるクラスとインターフェイスを決定します。 アプリケーション内で直接にも間接にも使用される予定がない型がある場合は、それらを除外できます。  
  
2.  CLS 準拠言語でソース ファイルを作成し、型を宣言します。 インポート変換プロセスの詳しい説明については、「[タイプ ライブラリからアセンブリへの変換の要約](http://msdn.microsoft.com/en-us/bf3f90c5-4770-4ab8-895c-3ba1055cc958)」を参照してください。 実際には、カスタム RCW を作成する場合は、[タイプ ライブラリ インポーター (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md) によって提供される型変換機能を手動で実行していることになります。 次のセクションの例では、IDL またはタイプ ライブラリ ファイル内の型と、C# コード内でそれぞれに対応する型について示します。  
  
3.  宣言が完成したら、他のマネージ ソース コードのコンパイルと同様に、このファイルをコンパイルします。  
  
4.  Tlbimp.exe でインポートする型と同様に、追加情報が必要となる場合があります。その場合には、コードに直接追加できます。 詳細については、「[方法 : 相互運用機能アセンブリを編集する](http://msdn.microsoft.com/en-us/16aacb20-2269-42bf-a812-b6a7df17e277)」を参照してください。  
  
## <a name="example"></a>例  
 IDL に含まれる `ISATest` インターフェイスおよび `SATest` クラスの例と、C# ソース コードのそれらに対応する型を次のコードに示します。  
  
 **IDL またはタイプ ライブラリ ファイル**  
  
```  
 [  
object,  
uuid(40A8C65D-2448-447A-B786-64682CBEF133),  
dual,  
helpstring("ISATest Interface"),  
pointer_default(unique)  
 ]  
interface ISATest : IDispatch  
 {  
[id(1), helpstring("method InSArray")]   
HRESULT InSArray([in] SAFEARRAY(int) *ppsa, [out,retval] int *pSum);  
 };  
 [  
uuid(116CCA1E-7E39-4515-9849-90790DA6431E),  
helpstring("SATest Class")  
 ]  
coclass SATest  
 {  
  [default] interface ISATest;  
 };  
```  
  
 **マネージ ソース コード内のラッパー**  
  
```csharp  
using System;  
using System.Runtime.InteropServices;  
using System.Runtime.CompilerServices;  
  
[assembly:Guid("E4A992B8-6F5C-442C-96E7-C4778924C753")]  
[assembly:ImportedFromTypeLib("SAServerLib")]  
namespace SAServer  
{  
 [ComImport]  
 [Guid("40A8C65D-2448-447A-B786-64682CBEF133")]  
 [TypeLibType(TypeLibTypeFlags.FLicensed)]  
 public interface ISATest  
 {  
  [DispId(1)]  
  //[MethodImpl(MethodImplOptions.InternalCall,  
  // MethodCodeType=MethodCodeType.Runtime)]  
  int InSArray( [MarshalAs(UnmanagedType.SafeArray,  
      SafeArraySubType=VarEnum.VT_I4)] ref int[] param );  
 }   
 [ComImport]  
 [Guid("116CCA1E-7E39-4515-9849-90790DA6431E")]  
 [ClassInterface(ClassInterfaceType.None)]  
 [TypeLibType(TypeLibTypeFlags.FCanCreate)]  
 public class SATest : ISATest  
 {  
  [DispId(1)]  
  [MethodImpl(MethodImplOptions.InternalCall,   
  MethodCodeType=MethodCodeType.Runtime)]  
  extern int ISATest.InSArray( [MarshalAs(UnmanagedType.SafeArray,   
  SafeArraySubType=VarEnum.VT_I4)] ref int[] param );  
 }  
}  
```  
  
## <a name="see-also"></a>参照  
 [ランタイム呼び出し可能ラッパーのカスタマイズ](http://msdn.microsoft.com/en-us/4652beaf-77d0-4f37-9687-ca193288c0be)  
 [COM のデータ型](http://msdn.microsoft.com/en-us/f93ae35d-a416-4218-8700-c8218cc90061)  
 [方法: 相互運用機能アセンブリの編集](http://msdn.microsoft.com/en-us/16aacb20-2269-42bf-a812-b6a7df17e277)  
 [タイプ ライブラリからアセンブリへの変換の要約](http://msdn.microsoft.com/en-us/bf3f90c5-4770-4ab8-895c-3ba1055cc958)  
 [Tlbimp.exe (タイプ ライブラリ インポーター)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md)  
 [Tlbexp.exe (タイプ ライブラリ エクスポーター)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md)
