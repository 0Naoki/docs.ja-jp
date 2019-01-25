---
title: Icorprofilerinfo 6::enumngenmodulemethodsinliningthismethod メソッド
ms.date: 03/30/2017
ms.assetid: b933dfe6-7833-40cb-aad8-40842dc3034f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 07b1c905e587708336ce690bbf3d187b2d21e5b9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54568154"
---
# <a name="icorprofilerinfo6enumngenmodulemethodsinliningthismethod-method"></a>Icorprofilerinfo 6::enumngenmodulemethodsinliningthismethod メソッド
[.NET Framework 4.6 以降のバージョンでサポートされます]  
  
 特定の NGen モジュールと特定のメソッドをインラインで定義されているすべてのメソッドには、列挙子を返します。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT EnumNgenModuleMethodsInliningThisMethod(  
        [in] ModuleID inlinersModuleId,  
        [in] ModuleID inlineeModuleId,  
        [in] mdMethodDef inlineeMethodId,  
        [out] BOOL *incompleteData,  
        [out] ICorProfilerMethodEnum** ppEnum  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `inlinersModuleId`  
 [in]NGen モジュールの識別子です。  
  
 `inlineeModuleId`  
 [in]定義するモジュールの識別子`inlineeMethodId`します。 詳細については、次の「解説」を参照してください。  
  
 `inlineeMethodId`  
 [in]インライン メソッドの識別子です。 詳細については、次の「解説」を参照してください。  
  
 `incompleteData`  
 [out]フラグを示すかどうか`ppEnum`特定のメソッドにはインライン展開のすべてのメソッドが含まれています。  詳細については、次の「解説」を参照してください。  
  
 `ppEnum`  
 [out]列挙子のアドレスへのポインター  
  
## <a name="remarks"></a>Remarks  
 `inlineeModuleId` `inlineeMethodId`インライン化されるメソッドの完全な識別子を形成します。 たとえば、モジュール`A`メソッドを定義します`Simple.Add`:  
  
```csharp  
Simple.Add(int a, int b)   
{ return a + b; }  
```  
  
 モジュール Bdefines `Fancy.AddTwice`:  
  
```csharp  
Fancy.AddTwice(int a, int b)   
{ return Simple.Add(a,b) + Simple.Add(a,b); }  
```  
  
 あることができます。`Fancy.AddTwice`インライン呼び出しに`SimpleAdd`します。 プロファイラーは、この列挙子を使用してモジュール B がインラインで定義されたすべてのメソッドを検索する可能性があります`Simple.Add`は、結果の列挙と`AddTwice`します。  `inlineeModuleId` モジュールの識別子は、 `A`、および`inlineeeMethodId`の識別子は、`Simple.Add(int a, int b)`します。  
  
 場合`incompleteData`関数の後に、列挙子は、すべてのメソッドがインライン展開の特定のメソッドを含んでいませんを返します。 これは、1 つの場合に発生することができますかより直接的または間接的な依存関係のインライン モジュールがまだ読み込まれていません。 プロファイラーは、データの正確性を必要とする場合は、複数のモジュールが読み込まれるときに、可能であれば 各モジュールの読み込み後に再試行する必要があります。  
  
 `EnumNgenModuleMethodsInliningThisMethod`メソッドを使用して、上の制限を回避する ReJIT のインライン化します。 ReJIT では、プロファイラーは、メソッドの実装を変更して、実行時にその新しいコードを作成できます。 たとえば、変更`Simple.Add`次のようにします。  
  
```csharp  
Simple.Add(int a, int b)   
{ return 42; }  
```  
  
 ただしため`Fancy.AddTwice`が既にインライン`Simple.Add`、以前と同じ動作を続行します。 呼び出し元がすべてのモジュールでインラインのすべてのメソッドを検索するがその制限を回避する`Simple.Add`を使用して、`ICorProfilerInfo5::RequestRejit`これらのメソッドの各します。 新しい動作が、メソッドは、再コンパイル、`Simple.Add`古い動作の代わりにします。  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。  
  
 **ヘッダー:** CorProf.idl、CorProf.h  
  
 **ライブラリ:** CorGuids.lib  
  
 **.NET Framework のバージョン:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>関連項目
- [ICorProfilerInfo6 インターフェイス](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md)
