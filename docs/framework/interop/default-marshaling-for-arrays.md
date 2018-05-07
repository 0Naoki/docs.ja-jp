---
title: 配列に対する既定のマーシャリング
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- interop marshaling, arrays
- arrays, interop marshaling
ms.assetid: 8a3cca8b-dd94-4e3d-ad9a-9ee7590654bc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b05ac1016710109110c3ff9d0d318a71fe0827f1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="default-marshaling-for-arrays"></a>配列に対する既定のマーシャリング
全体がマネージ コードで構成されるアプリケーションでは、共通言語ランタイムは、配列型を In/Out パラメーターとして渡します。 これに対し、相互運用マーシャラーは、既定で In パラメーターとして配列を渡します。  
  
 [ピン留め最適化](copying-and-pinning.md)を使用すると、同じアパートメント内のオブジェクトと対話するときに、blittable 配列を In/Out パラメーターとして操作しているように見せることができます。 ただし、後でコードをコンピューター間のプロキシを生成するために使用されるタイプ ライブラリにエクスポートし、そのライブラリがアパートメント間で呼び出しをマーシャリングするために使用される場合は、呼び出しで In パラメーターの動作を true に戻すことができます。  
  
 配列は本質的に複雑で、マネージ配列とアンマネージ配列間の違いが、他の非 blittable 型より多くの情報を保証します。 このトピックでは、マーシャリング配列に関する以下の情報を示します。  
  
-   [マネージ配列](#cpcondefaultmarshalingforarraysanchor1)  
  
-   [アンマネージ配列](#cpcondefaultmarshalingforarraysanchor2)  
  
-   [.NET コードへの配列パラメーターの引き渡し](#cpcondefaultmarshalingforarraysanchor3)  
  
-   [COM への配列の引き渡し](#cpcondefaultmarshalingforarraysanchor4)  
  
<a name="cpcondefaultmarshalingforarraysanchor1"></a>   
## <a name="managed-arrays"></a>マネージ配列  
 マネージ配列型は異なっても、<xref:System.Array?displayProperty=nameWithType> クラスはすべての配列型の基底クラスです。 **System.Array** クラスには、ランク、長さ、および配列の下限と上限を決定するためのプロパティに加え、配列のアクセス、並べ替え、検索、コピー、および作成するためのメソッドがあります。  
  
 これらの配列型は動的で、基底クラス ライブラリで定義されている対応する静的型はありません。 要素型とランクのそれぞれの組み合わせを配列の別個の型として考えると便利です。 このため、整数の 1 次元配列の型は double 型の 1 次元配列の型とは異なります。 同様に、整数の 2 次元配列は整数の 1 次元配列とは異なります。 型を比較するときに、配列の境界は考慮されません。  
  
 次の表に示すように、マネージ配列の任意のインスタンスは、特定の要素の型、ランク、および下限があります。  
  
|マネージ配列型|要素型|順位|下限|シグネチャの表記|  
|------------------------|------------------|----------|-----------------|------------------------|  
|**ELEMENT_TYPE_ARRAY**|型で指定。|ランクで指定。|必要に応じて境界で指定。|*型* **[** *n*、*m* **]**|  
|**ELEMENT_TYPE_CLASS**|不明|不明|不明|**System.Array**|  
|**ELEMENT_TYPE_SZARRAY**|型で指定。|1|0|*型* **[** *n* **]**|  
  
<a name="cpcondefaultmarshalingforarraysanchor2"></a>   
## <a name="unmanaged-arrays"></a>アンマネージ配列  
 アンマネージ配列は、COM スタイルのセーフ配列または固定長または可変長の C スタイルの配列です。 セーフ配列は、関連付けられた配列データの型、ランク、および境界を格納する自己記述型の配列です。 C スタイル配列は下限が 0 に固定された 1 次元型の配列です。 マーシャリング サービスには、両方の配列型の制限されたサポートがあります。  
  
<a name="cpcondefaultmarshalingforarraysanchor3"></a>   
## <a name="passing-array-parameters-to-net-code"></a>.NET コードへの配列パラメーターの引き渡し  
 C スタイル配列とセーフ配列は、どちらもセーフ配列または C スタイル配列としてアンマネージ コードから .NET コードに渡すことができます。 次の表に、アンマネージ型の値とインポートされた型を示します。  
  
|アンマネージ型|インポートされた型|  
|--------------------|-------------------|  
|**SafeArray(** *Type* **)**|**ELEMENT_TYPE_SZARRAY** **\<** *ConvertedType* **>**<br /><br /> ランク = 1、下限 = 0。 サイズはマネージ シグネチャで指定された場合にのみ判明します。 ランク = 1 または下限 = 0 ではないセーフ配列は、**SZARRAY** としてマーシャリングできません。|  
|*Type*  **[]**|**ELEMENT_TYPE_SZARRAY** **\<** *ConvertedType* **>**<br /><br /> ランク = 1、下限 = 0。 サイズはマネージ シグネチャで指定された場合にのみ判明します。|  
  
### <a name="safe-arrays"></a>セーフ配列  
 セーフ配列がタイプ ライブラリから .NET アセンブリにインポートされるときに、配列は既知の型 (**int** など) の 1 次元配列に変換されます。 パラメーターに適用される同じ型変換規則は、配列要素にも適用されます。 たとえば、**BSTR** 型のセーフ配列は文字列のマネージ配列になり、バリアントのセーフ配列はオブジェクトのマネージ配列になります。 **SAFEARRAY** 要素型はタイプ ライブラリからキャプチャされ、<xref:System.Runtime.InteropServices.UnmanagedType> 列挙型の **SAFEARRAY** 値に保存されます。  
  
 セーフ配列のランクと境界はタイプ ライブラリからは判断できないため、ランクは 1 に等しく下限は 0 に等しいと見なされます。 ランクと境界は、[タイプ ライブラリ インポーター (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md) によって生成されるマネージ シグネチャで定義する必要があります。 実行時にメソッドに渡されるランクが異なる場合、<xref:System.Runtime.InteropServices.SafeArrayRankMismatchException> がスローされます。 実行時に渡される配列の型が異なる場合、<xref:System.Runtime.InteropServices.SafeArrayTypeMismatchException> がスローされます。 次の例は、マネージ コードとアンマネージ コードでのセーフ配列を示しています。  
  
 **アンマネージ シグネチャ**  
  
```  
HRESULT New1([in] SAFEARRAY( int ) ar);  
HRESULT New2([in] SAFEARRAY( DATE ) ar);  
HRESULT New3([in, out] SAFEARRAY( BSTR ) *ar);  
```  
  
 **マネージ シグネチャ**  
  
```vb  
Sub New1(<MarshalAs(UnmanagedType.SafeArray, SafeArraySubType:=VT_I4)> _  
   ar() As Integer)  
Sub New2(<MarshalAs(UnmanagedType.SafeArray, SafeArraySubType:=VT_DATE)> _   
   ar() As DateTime)  
Sub New3(ByRef <MarshalAs(UnmanagedType.SafeArray, SafeArraySubType:=VT_BSTR)> _   
   ar() As String)  
```  
  
```csharp  
void New1([MarshalAs(UnmanagedType.SafeArray, SafeArraySubType=VT_I4)] int[] ar) ;  
void New2([MarshalAs(UnmanagedType.SafeArray, SafeArraySubType=VT_DATE)]   
   DateTime[] ar);  
void New3([MarshalAs(UnmanagedType.SafeArray, SafeArraySubType=VT_BSTR)]   
   ref String[] ar);  
```  
  
 多次元配列 (0 以外の値にバインドされたセーフ配列) は、Tlbimp.exe によって生成されたメソッド シグネチャが、**ELEMENT_TYPE_SZARRAY** ではなく **ELEMENT_TYPE_ARRAY** の要素型を示すように変更された場合に、マネージ コードにマーシャリングできます。 または、Tlbimp.exe で **/sysarray** スイッチを使用してすべての配列を <xref:System.Array?displayProperty=nameWithType> オブジェクトとしてインポートできます。 渡される配列が多次元配列だとわかっている場合は、Tlbimp.exe で生成された Microsoft Intermediate Language (MSIL) コードを編集してから再コンパイルすることができます。 MSIL コードの変更方法の詳細については、「[Customizing Runtime Callable Wrappers](https://msdn.microsoft.com/library/4652beaf-77d0-4f37-9687-ca193288c0be(v=vs.100))」(ランタイム呼び出し可能ラッパーのカスタマイズ) を参照してください。  
  
### <a name="c-style-arrays"></a>C スタイル配列  
 C スタイル配列がタイプ ライブラリから .NET アセンブリにインポートされると、その配列は **ELEMENT_TYPE_SZARRAY** に変換されます。  
  
 配列要素型は、タイプ ライブラリから決定され、インポート中は保持されます。 パラメーターに適用される同じ変換規則は、配列の要素にも適用されます。 たとえば、**LPStr** 型の配列は、**String** 型の配列になります。 Tlbimp.exe は配列要素型をキャプチャし、<xref:System.Runtime.InteropServices.MarshalAsAttribute> 属性をパラメーターに適用します。  
  
 配列ランクは 1 と等しいと見なされます。 ランクが 1 より大きい場合、配列は 1 次元配列として列優先順でマーシャリングされます。 下限は常に = 0 です。  
  
 タイプ ライブラリには、固定長または可変長の配列を含めることができます。 Tlbimp.exe は、タイプ ライブラリから固定長配列のみをインポートできます。これは、タイプ ライブラリに可変長配列をマーシャリングするために必要な情報が不足しているためです。 固定長配列では、サイズはタイプ ライブラリからインポートされ、パラメーターに適用される **MarshalAsAttribute** でキャプチャされます。  
  
 次の例に示すように、可変長配列を含むタイプ ライブラリを手動で定義する必要があります。  
  
 **アンマネージ シグネチャ**  
  
```  
HRESULT New1(int ar[10]);  
HRESULT New2(double ar[10][20]);  
HRESULT New3(LPWStr ar[10]);  
```  
  
 **マネージ シグネチャ**  
  
```vb  
Sub New1(<MarshalAs(UnmanagedType.LPArray, SizeConst=10)> _  
   ar() As Integer)  
Sub New2(<MarshalAs(UnmanagedType.LPArray, SizeConst=200)> _  
   ar() As Double)  
Sub New2(<MarshalAs(UnmanagedType.LPArray, _  
   ArraySubType=UnmanagedType.LPWStr, SizeConst=10)> _  
   ar() As String)  
```  
  
```csharp  
void New1([MarshalAs(UnmanagedType.LPArray, SizeConst=10)] int[] ar);  
void New2([MarshalAs(UnmanagedType.LPArray, SizeConst=200)] double[] ar);  
void New2([MarshalAs(UnmanagedType.LPArray,   
   ArraySubType=UnmanagedType.LPWStr, SizeConst=10)] String[] ar);  
```  
  
 インターフェイス定義言語 (IDL) ソース内の配列に **size_is** 属性または **length_is** 属性を適用してサイズをクライアントに伝達することができますが、Microsoft インターフェイス定義言語 (MIDL) コンパイラはその情報をタイプ ライブラリに伝達しません。 サイズがわからないと、相互運用マーシャリング サービスが配列要素をマーシャリングできません。 その結果、可変長配列は参照引数としてインポートされます。 例えば:  
  
 **アンマネージ シグネチャ**  
  
```  
HRESULT New1(int ar[]);  
HRESULT New2(int ArSize, [size_is(ArSize)] double ar[]);  
HRESULT New3(int ElemCnt, [length_is(ElemCnt)] LPStr ar[]);  
```  
  
 **マネージ シグネチャ**  
  
```vb  
Sub New1(ByRef ar As Integer)  
Sub New2(ByRef ar As Double)  
Sub New3(ByRef ar As String)  
```  
  
```csharp  
void New1(ref int ar);    
void New2(ref double ar);    
void New3(ref String ar);   
```  
  
 Tlbimp.exe によって生成された Microsoft Intermediate Language (MSIL) コードを編集して、マーシャラーに配列サイズを提供してから再コンパイルすることができます。 MSIL コードの変更方法の詳細については、「[Customizing Runtime Callable Wrappers](https://msdn.microsoft.com/library/4652beaf-77d0-4f37-9687-ca193288c0be(v=vs.100))」(ランタイム呼び出し可能ラッパーのカスタマイズ) を参照してください。 配列内の要素の数を示すには、次の方法のいずれかの方法で、<xref:System.Runtime.InteropServices.MarshalAsAttribute> 型をマネージ メソッド定義の配列パラメーターに適用します。  
  
-   配列内の要素数を含む別のパラメーターを特定します。 パラメーターは位置によって識別され、最初のパラメーターは番号 0 から始まります。     
  
    ```vb  
    Sub [New](ElemCnt As Integer, _  
       \<MarshalAs(UnmanagedType.LPArray, SizeParamIndex:=1)> _  
       ar() As Integer)  
    ```  
  
    ```csharp  
    void New(  
       int ElemCnt,   
       [MarshalAs(UnmanagedType.LPArray, SizeParamIndex=0)] int[] ar );  
    ```  
  
-   配列のサイズを定数として定義します。 例えば:  
  
    ```vb  
    Sub [New](\<MarshalAs(UnmanagedType.LPArray, SizeConst:=128)> _  
       ar() As Integer)  
    ```  
  
    ```csharp  
    void New(  
       [MarshalAs(UnmanagedType.LPArray, SizeConst=128)] int[] ar );  
    ```  
  
 アンマネージ コードからマネージ コードに配列をマーシャリングする場合、マーシャラーはパラメーターに関連付けられた **MarshalAsAttribute** をチェックして配列サイズを決定します。 配列サイズが指定されていない場合は、1 つの要素のみがマーシャリングされます。  
  
> [!NOTE]
>  **MarshalAsAttribute** は、マネージ配列のアンマネージ コードへのマーシャリングには影響しません。 その方向では、配列サイズは検査で決定されます。 マネージ配列のサブセットをマーシャリングする方法はありません。  
  
 相互運用マーシャラーは、**CoTaskMemAlloc** メソッドと **CoTaskMemFree** メソッドを使用してメモリの割り当てと取得を行います。 アンマネージ コードによって実行されるメモリの割り当てでは、これらのメソッドも使用する必要があります。  
  
<a name="cpcondefaultmarshalingforarraysanchor4"></a>   
## <a name="passing-arrays-to-com"></a>COM への配列の引き渡し  
 すべてのマネージ配列型は、マネージ コードからアンマネージ コードに渡すことができます。 次の表に示すように、マネージ型とそれに適用される属性に応じて、セーフ配列または C スタイル配列として配列にアクセスできます。  
  
|マネージ配列型|エクスポート|  
|------------------------|-----------------|  
|**ELEMENT_TYPE_SZARRAY** **\<** *type* **>**|<xref:System.Runtime.InteropServices.UnmanagedType> **.SafeArray(** *type* **)**<br /><br /> **UnmanagedType.LPArray**<br /><br /> 型はシグネチャで提供されます。 ランクは常に 1 で、下限は常に 0 です。 サイズは実行時に常に把握されています。|  
|**ELEMENT_TYPE_ARRAY** **\<** *type* **>** **\<** *rank* **>**[**\<** *bounds* **>**]|**UnmanagedType.SafeArray(** *type* **)**<br /><br /> **UnmanagedType.LPArray**<br /><br /> 型、ランク、境界はシグネチャで提供されます。 サイズは実行時に常に把握されています。|  
|**ELEMENT_TYPE_CLASS** **\<**<xref:System.Array?displayProperty=nameWithType>**>**|**UT_Interface**<br /><br /> **UnmanagedType.SafeArray(** *type* **)**<br /><br /> 型、ランク、境界、およびサイズは実行時に常に把握されています。|  
  
 LPSTR または LPWSTR を含む構造体の配列に関連する OLE オートメーションの制限があります。  そのため、**String** フィールドは **UnmanagedType.BSTR** としてマーシャリングする必要があります。 この操作を行わない場合、例外がスローされます。  
  
### <a name="elementtypeszarray"></a>ELEMENT_TYPE_SZARRAY  
 **ELEMENT_TYPE_SZARRAY** パラメーター (1 次元配列) を含むメソッドが .NET アセンブリからタイプ ライブラリにエクスポートされるときに、配列パラメーターが特定の型の **SAFEARRAY** に変換されます。 同じ変換規則が配列要素型に適用されます。 マネージ配列の内容はマネージ メモリから **SAFEARRAY** に自動的にコピーされます。 例えば:  
  
#### <a name="managed-signature"></a>マネージ シグネチャ  
  
```vb  
Sub [New](ar() As Long)  
Sub [New](ar() As String)  
```  
  
```csharp  
void New(long[] ar );  
void New(String[] ar );  
```  
  
#### <a name="unmanaged-signature"></a>アンマネージ シグネチャ  
  
```  
HRESULT New([in] SAFEARRAY( long ) ar);   
HRESULT New([in] SAFEARRAY( BSTR ) ar);  
```  
  
 セーフ配列のランクは常に 1 で、下限は常に 0 です。 サイズは実行時に渡されるマネージ配列のサイズによって決まります。  
  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 属性を使用することで、配列を C スタイル配列としてマーシャリングすることもできます。 例えば:  
  
#### <a name="managed-signature"></a>マネージ シグネチャ  
  
```vb  
Sub [New](<MarshalAs(UnmanagedType.LPArray, SizeParamIndex:=1)> _  
   ar() As Long, size as Integer)  
Sub [New](<MarshalAs(UnmanagedType.LPArray, SizeParamIndex:=1)> _  
   ar() As String, size as Integer)  
Sub [New](<MarshalAs(UnmanagedType.LPArray, _  
   ArraySubType= UnmanagedType.LPStr, SizeParamIndex:=1)> _  
   ar() As String, size as Integer)  
```  
  
```csharp  
void New([MarshalAs(UnmanagedType.LPArray, SizeParamIndex=1)]   
   long [] ar, int size );  
void New([MarshalAs(UnmanagedType.LPArray, SizeParamIndex=1)]   
   String [] ar, int size );  
void New([MarshalAs(UnmanagedType.LPArray, ArraySubType=   
   UnmanagedType.LPStr, SizeParamIndex=1)]   
   String [] ar, int size );  
```  
  
#### <a name="unmanaged-signature"></a>アンマネージ シグネチャ  
  
```  
HRESULT New(long ar[]);   
HRESULT New(BSTR ar[]);   
HRESULT New(LPStr ar[]);  
```  
  
 マーシャラーには配列をマーシャリングするために必要な長さ情報がありますが、配列の長さは通常、呼び出し先に長さを伝えるために個別の引数として渡されます。  
  
### <a name="elementtypearray"></a>ELEMENT_TYPE_ARRAY  
 **ELEMENT_TYPE_ARRAY** パラメーターを含むメソッドが .NET アセンブリからタイプ ライブラリにエクスポートされるときに、配列パラメーターが特定の型の **SAFEARRAY** に変換されます。 マネージ配列の内容はマネージ メモリから **SAFEARRAY** に自動的にコピーされます。 例えば:  
  
#### <a name="managed-signature"></a>マネージ シグネチャ  
  
```vb  
Sub [New](ar(,) As Long)  
Sub [New](ar(,) As String)  
```  
  
```csharp  
void New( long [,] ar );  
void New( String [,] ar );  
```  
  
#### <a name="unmanaged-signature"></a>アンマネージ シグネチャ  
  
```  
HRESULT New([in] SAFEARRAY( long ) ar);   
HRESULT New([in] SAFEARRAY( BSTR ) ar);  
```  
  
 セーフ配列のランク、サイズ、およ境界は、マネージ配列の特性によって実行時に決定されます。  
  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 属性を適用することで、配列を C スタイル配列としてマーシャリングすることもできます。 例えば:  
  
#### <a name="managed-signature"></a>マネージ シグネチャ  
  
```vb  
Sub [New](<MarshalAs(UnmanagedType.LPARRAY, SizeParamIndex:=1)> _  
   ar(,) As Long, size As Integer)  
Sub [New](<MarshalAs(UnmanagedType.LPARRAY, _  
   ArraySubType:=UnmanagedType.LPStr, SizeParamIndex:=1)> _  
   ar(,) As String, size As Integer)  
```  
  
```csharp  
void New([MarshalAs(UnmanagedType.LPARRAY, SizeParamIndex=1)]   
   long [,] ar, int size );  
void New([MarshalAs(UnmanagedType.LPARRAY,   
   ArraySubType= UnmanagedType.LPStr, SizeParamIndex=1)]   
   String [,] ar, int size );  
```  
  
#### <a name="unmanaged-signature"></a>アンマネージ シグネチャ  
  
```  
HRESULT New(long ar[]);   
HRESULT New(LPStr ar[]);  
```  
  
 入れ子にされた配列をマーシャリングすることはできません。 たとえば、次のシグネチャを[タイプ ライブラリ エクスポーター (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md) を使用してエクスポートすると、エラーが発生します。  
  
#### <a name="managed-signature"></a>マネージ シグネチャ  
  
```vb  
Sub [New](ar()()() As Long)  
```  
  
```csharp  
void New(long [][][] ar );  
```  
  
### <a name="elementtypeclass-systemarray"></a>ELEMENT_TYPE_CLASS \<System.Array>  
 <xref:System.Array?displayProperty=nameWithType> パラメーターを含むメソッドが .NET アセンブリからタイプ ライブラリにエクスポートされるときに、配列パラメーターが特定の型の **_Array** インターフェイスに変換されます。 マネージ配列の内容には、**_Array** インターフェイスのメソッドとプロパティを介してのみアクセスできます。 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 属性を使用することで、**System.Array** を **SAFEARRAY** としてマーシャリングすることもできます。 セーフ配列としてマーシャリングすると、配列要素はバリアントとしてマーシャリングされます。 例えば:  
  
#### <a name="managed-signature"></a>マネージ シグネチャ  
  
```vb  
Sub New1( ar As System.Array )  
Sub New2( <MarshalAs(UnmanagedType.Safe array)> ar As System.Array )  
```  
  
```csharp  
void New1( System.Array ar );  
void New2( [MarshalAs(UnmanagedType.Safe array)] System.Array ar );  
```  
  
#### <a name="unmanaged-signature"></a>アンマネージ シグネチャ  
  
```  
HRESULT New([in] _Array *ar);   
HRESULT New([in] SAFEARRAY(VARIANT) ar);  
```  
  
### <a name="arrays-within-structures"></a>構造体内の配列  
 アンマネージ構造体には、埋め込まれた配列を含めることができます。 既定では、これらの埋め込まれた配列フィールドは SAFEARRAY としてマーシャリングされます。 次の例では、`s1` が構造体そのものに直接割り当てられている埋め込まれた配列です。  
  
#### <a name="unmanaged-representation"></a>アンマネージ表現  
  
```  
struct MyStruct {  
    short s1[128];  
}  
```  
  
 <xref:System.Runtime.InteropServices.UnmanagedType> としてマーシャリングできる配列で、<xref:System.Runtime.InteropServices.MarshalAsAttribute> フィールドを設定する必要があります。 サイズは定数としてのみ設定できます。 次のコードは、`MyStruct` の対応するマネージ定義を示しています。  
  
```vb  
Public Structure <StructLayout(LayoutKind.Sequential)> MyStruct  
   Public <MarshalAs(UnmanagedType.ByValArray, SizeConst := 128)> _  
     s1() As Short  
End Structure  
```  
  
```csharp  
[StructLayout(LayoutKind.Sequential)]  
public struct MyStruct {  
   [MarshalAs(UnmanagedType.ByValArray, SizeConst=128)] public short[] s1;  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [既定のマーシャリング動作](default-marshaling-behavior.md)  
 [Blittable 型と非 Blittable 型](blittable-and-non-blittable-types.md)  
 [方向属性](https://msdn.microsoft.com/library/241ac5b5-928e-4969-8f58-1dbc048f9ea2(v=vs.100))  
 [コピーと固定](copying-and-pinning.md)
