---
title: "マネージ コードでのプロトタイプの作成 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "COM 相互運用機能, DLL 関数"
  - "COM 相互運用機能, プラットフォーム呼び出し"
  - "DLL 関数"
  - "相互運用 (アンマネージ コードとの), DLL 関数"
  - "相互運用 (アンマネージ コードとの), プラットフォーム呼び出し"
  - "オブジェクト フィールド (プラットフォーム呼び出しにおける)"
  - "プラットフォーム呼び出し, 作成 (プロトタイプを)"
  - "プラットフォーム呼び出し, オブジェクト フィールド"
  - "プロトタイプ (マネージ コード内の)"
  - "アンマネージ関数"
ms.assetid: ecdcf25d-cae3-4f07-a2b6-8397ac6dc42d
caps.latest.revision: 22
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 21
---
# マネージ コードでのプロトタイプの作成
このトピックは、アンマネージ関数にアクセスする方法について説明し、マネージ コードでメソッドの定義の注釈を設定するいくつかの属性フィールドを紹介しています。  プラットフォームの起動で使用する NET ベースの宣言を作成する方法を示す例については、「[プラットフォーム呼び出しによるデータのマーシャリング](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)」を参照してください。  
  
 マネージ コードからアンマネージ DLL 関数にアクセスする前に、関数の名前とエクスポートする DLL の名前を知っている必要があります。  この情報を使用すると、マネージ DLL に実装されているアンマネージ関数の定義の作成を開始できます。  さらに、プラットフォーム呼び出しが関数を作成し、関数間でデータをマーシャリングする方法を調整できます。  
  
> [!NOTE]
>  文字列を割り当てる Win32 API 関数を使用して、`LocalFree` などのメソッドを使用して文字列を解放できます。  プラットフォーム呼び出しは、このようなパラメーターを異なる方法で処理します。  プラットフォーム呼び出しでは、パラメーターを `String` 型の代わりに `IntPtr` 型にします。  <xref:System.Runtime.InteropServices.Marshal?displayProperty=fullName> クラスにより提供されるメソッドを使用して、型を手動で文字列に変換し、手動で解放します。  
  
## 宣言の基本  
 アンマネージ関数に対するマネージ定義は、次の例で確認できるように、言語に依存します。  完全なコード例については、「[プラットフォーム呼び出しの例](../../../docs/framework/interop/platform-invoke-examples.md)」を参照してください。  
  
```vb  
Imports System.Runtime.InteropServices  
Public Class Win32  
    Declare Auto Function MessageBox Lib "user32.dll" _  
       (ByVal hWnd As Integer, _  
        ByVal txt As String, ByVal caption As String, _  
        ByVal Typ As Integer) As IntPtr  
End Class  
```  
  
 <xref:System.Runtime.InteropServices.DllImportAttribute.BestFitMapping>、<xref:System.Runtime.InteropServices.DllImportAttribute.CallingConvention>、<xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling>、<xref:System.Runtime.InteropServices.DllImportAttribute.PreserveSig>、<xref:System.Runtime.InteropServices.DllImportAttribute.SetLastError>、または <xref:System.Runtime.InteropServices.DllImportAttribute.ThrowOnUnmappableChar> の各フィールドを [!INCLUDE[vbprvbext](../../../includes/vbprvbext-md.md)] 宣言に適用するには、`Declare` ステートメントの代わりに <xref:System.Runtime.InteropServices.DllImportAttribute> 属性を使用する必要があります。  
  
```vb  
Imports System.Runtime.InteropServices  
Public Class Win32  
   <DllImport ("user32.dll", CharSet := CharSet.Auto)> _  
   Public Shared Function MessageBox (ByVal hWnd As Integer, _  
        ByVal txt As String, ByVal caption As String, _  
        ByVal Typ As Integer) As IntPtr  
   End Function  
End Class  
  
```  
  
```csharp  
using System.Runtime.InteropServices;  
[DllImport("user32.dll")]  
    public static extern IntPtr MessageBox(int hWnd, String text,   
                                       String caption, uint type);  
  
```  
  
```cpp  
using namespace System::Runtime::InteropServices;  
[DllImport("user32.dll")]  
    extern "C" IntPtr MessageBox(int hWnd, String* pText,  
    String* pCaption unsigned int uType);  
```  
  
## 定義の調整  
 明示的に設定するかどうかに関係なく、属性フィールドは作業はマネージ コードの動作を動作中に定義します。  プラットフォーム呼び出しは、アセンブリ内のメタデータとして存在するさまざまなフィールドで設定された既定値どおりに動作します。  1 つまたは複数のフィールドの値を調整することによって、この既定の動作を変更することができます。  多くの場合、<xref:System.Runtime.InteropServices.DllImportAttribute> を使用して値を設定します。  
  
 次の表では、プラットフォーム呼び出しに関連する属性フィールドの完全なセットを一覧表示します。  各フィールドについては、表に既定値とこれらのフィールドを使用してアンマネージ DLL 関数を定義する方法に関する情報へのリンクが含まれます。  
  
|フィールド|説明|  
|-----------|--------|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.BestFitMapping>|最適なマッピングを有効または無効にします。|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.CallingConvention>|メソッドの引数を渡すときに使用する呼び出し規約を指定します。  既定値は `WinAPI` で、32 ビットの Intel ベース プラットフォームの `__stdcall` に対応します。|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.CharSet>|名前修飾および文字列の引数を関数にマーシャリングする方法を管理します。  既定値は、`CharSet.Ansi` です。|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint>|呼び出される DLL エントリ ポイントを指定します。|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling>|文字セットに対応するエントリ ポイントを変更する必要があるかどうかを制御します。  既定値は、プログラミング言語によって異なります。|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.PreserveSig>|マネージ メソッドのシグネチャが、HRESULT を返すアンマネージ シグネチャに変換され、戻り値の追加の \[out, retval\] 引数を持つかどうかを制御します。<br /><br /> 既定値は `true` です \(シグネチャは変換されません\)。|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.SetLastError>|呼び出し元が `Marshal.GetLastWin32Error` API の関数を使用して、メソッドの実行中にエラーが発生したかどうかを判断できるようにします。  Visual Basic では既定値は `true`、C\# および C\+\+ では既定値は `false` です。|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.ThrowOnUnmappableChar>|ANSI の"?" 文字に変換されるマップできない Unicode 文字での例外のスローを制御します。|  
  
 詳細なリファレンス情報については、「[DllImportAttribute クラス](frlrfSystemRuntimeInteropServicesDllImportAttributeClassTopic)」を参照してください。  
  
## プラットフォーム呼び出しのセキュリティに関する考慮事項  
 <xref:System.Security.Permissions.SecurityAction> 列挙型の `Assert`、`Deny`、および `PermitOnly` のメンバーは、*スタック ウォーク修飾子*と呼ばれます。  プラットフォーム呼び出しの宣言および COM インターフェイス定義言語 \(IDL\) ステートメントの宣言属性として使用される場合、これらのメンバーは無視されます。  
  
### プラットフォーム呼び出しの例  
 このセクションのプラットフォーム呼び出しのサンプルは、`RegistryPermission` スタック ウォーク修飾子を持つ属性の使用方法を示します。  
  
 次のコード例では、<xref:System.Security.Permissions.SecurityAction> `Assert`、`Deny`、および `PermitOnly` 修飾子は無視されます。  
  
```  
[DllImport("MyClass.dll", EntryPoint = "CallRegistryPermission")]  
[RegistryPermission(SecurityAction.Assert, Unrestricted = true)]  
    private static extern bool CallRegistryPermissionAssert();  
  
[DllImport("MyClass.dll", EntryPoint = "CallRegistryPermission")]  
[RegistryPermission(SecurityAction.Deny, Unrestricted = true)]  
    private static extern bool CallRegistryPermissionDeny();  
  
[DllImport("MyClass.dll", EntryPoint = "CallRegistryPermission")]  
[RegistryPermission(SecurityAction.PermitOnly, Unrestricted = true)]  
    private static extern bool CallRegistryPermissionDeny();  
```  
  
 ただし、次の例の `Demand` 修飾子は受け入れられます。  
  
```  
[DllImport("MyClass.dll", EntryPoint = "CallRegistryPermission")]  
[RegistryPermission(SecurityAction.Demand, Unrestricted = true)]  
    private static extern bool CallRegistryPermissionDeny();  
```  
  
 プラットフォーム呼び出しを含む \(ラップする\) クラスに配置されている場合、<xref:System.Security.Permissions.SecurityAction> 修飾子は正常に機能します。  
  
```cpp  
[RegistryPermission(SecurityAction.Demand, Unrestricted = true)]  
public ref class PInvokeWrapper  
{  
public:  
[DllImport("MyClass.dll", EntryPoint = "CallRegistryPermission")]  
    private static extern bool CallRegistryPermissionDeny();  
};  
```  
  
```csharp  
[RegistryPermission(SecurityAction.Demand, Unrestricted = true)]  
class PInvokeWrapper  
{  
[DllImport("MyClass.dll", EntryPoint = "CallRegistryPermission")]  
    private static extern bool CallRegistryPermissionDeny();  
}  
  
```  
  
 <xref:System.Security.Permissions.SecurityAction> 修飾子は、プラットフォーム呼び出しの呼び出し元に配置されたネストしたシナリオでも正しく動作します。  
  
```cpp  
{  
public ref class PInvokeWrapper  
public:  
    [DllImport("MyClass.dll", EntryPoint = "CallRegistryPermission")]  
    private static extern bool CallRegistryPermissionDeny();  
  
    [RegistryPermission(SecurityAction.Demand, Unrestricted = true)]  
    public static bool CallRegistryPermission()  
    {  
     return CallRegistryPermissionInternal();  
    }  
};  
```  
  
```csharp  
class PInvokeScenario  
{  
    [DllImport("MyClass.dll", EntryPoint = "CallRegistryPermission")]  
    private static extern bool CallRegistryPermissionInternal();  
  
    [RegistryPermission(SecurityAction.Assert, Unrestricted = true)]  
    public static bool CallRegistryPermission()  
    {  
     return CallRegistryPermissionInternal();  
    }  
}  
```  
  
#### COM 相互運用機能の例  
 このセクションの次の COM 相互運用機能の例は、スタック ウォーク修飾子を持つ `RegistryPermission` 属性の使用方法を示します。  
  
 次の COM 相互運用機能のインターフェイスの宣言は、前のセクションのプラットフォーム呼び出しの例と同様に、`Assert`、`Deny`、および `PermitOnly` の修飾子を無視します。  
  
```  
[ComImport, Guid("12345678-43E6-43c9-9A13-47F40B338DE0")]  
interface IAssertStubsItf  
{  
[RegistryPermission(SecurityAction.Assert, Unrestricted = true)]  
    bool CallRegistryPermission();  
[FileIOPermission(SecurityAction.Assert, Unrestricted = true)]  
    bool CallFileIoPermission();  
}  
  
[ComImport, Guid("12345678-43E6-43c9-9A13-47F40B338DE0")]  
interface IDenyStubsItf  
{  
[RegistryPermission(SecurityAction.Deny, Unrestricted = true)]  
    bool CallRegistryPermission();  
[FileIOPermission(SecurityAction.Deny, Unrestricted = true)]  
    bool CallFileIoPermission();  
}  
  
[ComImport, Guid("12345678-43E6-43c9-9A13-47F40B338DE0")]  
interface IAssertStubsItf  
{  
[RegistryPermission(SecurityAction.PermitOnly, Unrestricted = true)]  
    bool CallRegistryPermission();  
[FileIOPermission(SecurityAction.PermitOnly, Unrestricted = true)]  
    bool CallFileIoPermission();  
}  
  
```  
  
 さらに、次の例に示すように、`Demand` 修飾子は COM 相互運用機能のインターフェイスの宣言のシナリオでは許可されません。  
  
```  
[ComImport, Guid("12345678-43E6-43c9-9A13-47F40B338DE0")]  
interface IDemandStubsItf  
{  
[RegistryPermission(SecurityAction.Demand, Unrestricted = true)]  
    bool CallRegistryPermission();  
[FileIOPermission(SecurityAction.Demand, Unrestricted = true)]  
    bool CallFileIoPermission();  
}  
```  
  
## 参照  
 [アンマネージ DLL 関数の処理](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)   
 [エントリ ポイントの指定](../../../docs/framework/interop/specifying-an-entry-point.md)   
 [文字セットの指定](../../../docs/framework/interop/specifying-a-character-set.md)   
 [プラットフォーム呼び出しの例](../../../docs/framework/interop/platform-invoke-examples.md)   
 [Platform Invoke Security Considerations](http://msdn.microsoft.com/ja-jp/bbcc67f7-50b5-4917-88ed-cb15470409fb)   
 [DLL 内の関数の識別](../../../docs/framework/interop/identifying-functions-in-dlls.md)   
 [DLL 関数を保持するクラスの作成](../../../docs/framework/interop/creating-a-class-to-hold-dll-functions.md)   
 [DLL 関数の呼び出し](../../../docs/framework/interop/calling-a-dll-function.md)