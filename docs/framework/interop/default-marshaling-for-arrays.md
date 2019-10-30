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
ms.openlocfilehash: 8505f4c742fb002be249ab069708f7f768c672df
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123574"
---
# <a name="default-marshaling-for-arrays"></a><span data-ttu-id="a598f-102">配列に対する既定のマーシャリング</span><span class="sxs-lookup"><span data-stu-id="a598f-102">Default Marshaling for Arrays</span></span>
<span data-ttu-id="a598f-103">全体がマネージド コードで構成されるアプリケーションでは、共通言語ランタイムは、配列型を In/Out パラメーターとして渡します。</span><span class="sxs-lookup"><span data-stu-id="a598f-103">In an application consisting entirely of managed code, the common language runtime passes array types as In/Out parameters.</span></span> <span data-ttu-id="a598f-104">これに対し、相互運用マーシャラーは、既定で In パラメーターとして配列を渡します。</span><span class="sxs-lookup"><span data-stu-id="a598f-104">In contrast, the interop marshaler passes an array as In parameters by default.</span></span>  
  
 <span data-ttu-id="a598f-105">[ピン留め最適化](copying-and-pinning.md)を使用すると、同じアパートメント内のオブジェクトと対話するときに、blittable 配列を In/Out パラメーターとして操作しているように見せることができます。</span><span class="sxs-lookup"><span data-stu-id="a598f-105">With [pinning optimization](copying-and-pinning.md), a blittable array can appear to operate as an In/Out parameter when interacting with objects in the same apartment.</span></span> <span data-ttu-id="a598f-106">ただし、後でコードをコンピューター間のプロキシを生成するために使用されるタイプ ライブラリにエクスポートし、そのライブラリがアパートメント間で呼び出しをマーシャリングするために使用される場合は、呼び出しで In パラメーターの動作を true に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="a598f-106">However, if you later export the code to a type library used to generate the cross-machine proxy, and that library is used to marshal your calls across apartments, the calls can revert to true In parameter behavior.</span></span>  
  
 <span data-ttu-id="a598f-107">配列は本質的に複雑で、マネージド配列とアンマネージド配列間の違いが、他の非 blittable 型より多くの情報を保証します。</span><span class="sxs-lookup"><span data-stu-id="a598f-107">Arrays are complex by nature, and the distinctions between managed and unmanaged arrays warrant more information than other non-blittable types.</span></span>  
  
## <a name="managed-arrays"></a><span data-ttu-id="a598f-108">マネージド配列</span><span class="sxs-lookup"><span data-stu-id="a598f-108">Managed Arrays</span></span>  
 <span data-ttu-id="a598f-109">マネージド配列型は異なっても、<xref:System.Array?displayProperty=nameWithType> クラスはすべての配列型の基底クラスです。</span><span class="sxs-lookup"><span data-stu-id="a598f-109">Managed array types can vary; however, the <xref:System.Array?displayProperty=nameWithType> class is the base class of all array types.</span></span> <span data-ttu-id="a598f-110">**System.Array** クラスには、ランク、長さ、および配列の下限と上限を決定するためのプロパティに加え、配列のアクセス、並べ替え、検索、コピー、および作成するためのメソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="a598f-110">The **System.Array** class has properties for determining the rank, length, and lower and upper bounds of an array, as well as methods for accessing, sorting, searching, copying, and creating arrays.</span></span>  
  
 <span data-ttu-id="a598f-111">これらの配列型は動的で、基底クラス ライブラリで定義されている対応する静的型はありません。</span><span class="sxs-lookup"><span data-stu-id="a598f-111">These array types are dynamic and do not have a corresponding static type defined in the base class library.</span></span> <span data-ttu-id="a598f-112">要素型とランクのそれぞれの組み合わせを配列の別個の型として考えると便利です。</span><span class="sxs-lookup"><span data-stu-id="a598f-112">It is convenient to think of each combination of element type and rank as a distinct type of array.</span></span> <span data-ttu-id="a598f-113">このため、整数の 1 次元配列の型は double 型の 1 次元配列の型とは異なります。</span><span class="sxs-lookup"><span data-stu-id="a598f-113">Therefore, a one-dimensional array of integers is of a different type than a one-dimensional array of double types.</span></span> <span data-ttu-id="a598f-114">同様に、整数の 2 次元配列は整数の 1 次元配列とは異なります。</span><span class="sxs-lookup"><span data-stu-id="a598f-114">Similarly a two-dimensional array of integers is different from a one-dimensional array of integers.</span></span> <span data-ttu-id="a598f-115">型を比較するときに、配列の境界は考慮されません。</span><span class="sxs-lookup"><span data-stu-id="a598f-115">The bounds of the array are not considered when comparing types.</span></span>  
  
 <span data-ttu-id="a598f-116">次の表に示すように、マネージド配列の任意のインスタンスは、特定の要素の型、ランク、および下限があります。</span><span class="sxs-lookup"><span data-stu-id="a598f-116">As the following table shows, any instance of a managed array must be of a specific element type, rank, and lower bound.</span></span>  
  
|<span data-ttu-id="a598f-117">マネージド配列型</span><span class="sxs-lookup"><span data-stu-id="a598f-117">Managed array type</span></span>|<span data-ttu-id="a598f-118">要素型</span><span class="sxs-lookup"><span data-stu-id="a598f-118">Element type</span></span>|<span data-ttu-id="a598f-119">順位</span><span class="sxs-lookup"><span data-stu-id="a598f-119">Rank</span></span>|<span data-ttu-id="a598f-120">下限</span><span class="sxs-lookup"><span data-stu-id="a598f-120">Lower bound</span></span>|<span data-ttu-id="a598f-121">シグネチャの表記</span><span class="sxs-lookup"><span data-stu-id="a598f-121">Signature notation</span></span>|  
|------------------------|------------------|----------|-----------------|------------------------|  
|<span data-ttu-id="a598f-122">**ELEMENT_TYPE_ARRAY**</span><span class="sxs-lookup"><span data-stu-id="a598f-122">**ELEMENT_TYPE_ARRAY**</span></span>|<span data-ttu-id="a598f-123">型で指定。</span><span class="sxs-lookup"><span data-stu-id="a598f-123">Specified by type.</span></span>|<span data-ttu-id="a598f-124">ランクで指定。</span><span class="sxs-lookup"><span data-stu-id="a598f-124">Specified by rank.</span></span>|<span data-ttu-id="a598f-125">必要に応じて境界で指定。</span><span class="sxs-lookup"><span data-stu-id="a598f-125">Optionally specified by bounds.</span></span>|<span data-ttu-id="a598f-126">*type* **[** *n*,*m* **]**</span><span class="sxs-lookup"><span data-stu-id="a598f-126">*type* **[** *n*,*m* **]**</span></span>|  
|<span data-ttu-id="a598f-127">**ELEMENT_TYPE_CLASS**</span><span class="sxs-lookup"><span data-stu-id="a598f-127">**ELEMENT_TYPE_CLASS**</span></span>|<span data-ttu-id="a598f-128">不明</span><span class="sxs-lookup"><span data-stu-id="a598f-128">Unknown</span></span>|<span data-ttu-id="a598f-129">不明</span><span class="sxs-lookup"><span data-stu-id="a598f-129">Unknown</span></span>|<span data-ttu-id="a598f-130">不明</span><span class="sxs-lookup"><span data-stu-id="a598f-130">Unknown</span></span>|<span data-ttu-id="a598f-131">**System.Array**</span><span class="sxs-lookup"><span data-stu-id="a598f-131">**System.Array**</span></span>|  
|<span data-ttu-id="a598f-132">**ELEMENT_TYPE_SZARRAY**</span><span class="sxs-lookup"><span data-stu-id="a598f-132">**ELEMENT_TYPE_SZARRAY**</span></span>|<span data-ttu-id="a598f-133">型で指定。</span><span class="sxs-lookup"><span data-stu-id="a598f-133">Specified by type.</span></span>|<span data-ttu-id="a598f-134">1</span><span class="sxs-lookup"><span data-stu-id="a598f-134">1</span></span>|<span data-ttu-id="a598f-135">0</span><span class="sxs-lookup"><span data-stu-id="a598f-135">0</span></span>|<span data-ttu-id="a598f-136">*type* **[** *n* **]**</span><span class="sxs-lookup"><span data-stu-id="a598f-136">*type* **[** *n* **]**</span></span>|  
  
## <a name="unmanaged-arrays"></a><span data-ttu-id="a598f-137">アンマネージ配列</span><span class="sxs-lookup"><span data-stu-id="a598f-137">Unmanaged Arrays</span></span>  
 <span data-ttu-id="a598f-138">アンマネージ配列は、COM スタイルのセーフ配列または固定長または可変長の C スタイルの配列です。</span><span class="sxs-lookup"><span data-stu-id="a598f-138">Unmanaged arrays are either COM-style safe arrays or C-style arrays with fixed or variable length.</span></span> <span data-ttu-id="a598f-139">セーフ配列は、関連付けられた配列データの型、ランク、および境界を格納する自己記述型の配列です。</span><span class="sxs-lookup"><span data-stu-id="a598f-139">Safe arrays are self-describing arrays that carry the type, rank, and bounds of the associated array data.</span></span> <span data-ttu-id="a598f-140">C スタイル配列は下限が 0 に固定された 1 次元型の配列です。</span><span class="sxs-lookup"><span data-stu-id="a598f-140">C-style arrays are one-dimensional typed arrays with a fixed lower bound of 0.</span></span> <span data-ttu-id="a598f-141">マーシャリング サービスには、両方の配列型の制限されたサポートがあります。</span><span class="sxs-lookup"><span data-stu-id="a598f-141">The marshaling service has limited support for both types of arrays.</span></span>  
  
## <a name="passing-array-parameters-to-net-code"></a><span data-ttu-id="a598f-142">.NET コードへの配列パラメーターの引き渡し</span><span class="sxs-lookup"><span data-stu-id="a598f-142">Passing Array Parameters to .NET Code</span></span>  
 <span data-ttu-id="a598f-143">C スタイル配列とセーフ配列は、どちらもセーフ配列または C スタイル配列としてアンマネージ コードから .NET コードに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="a598f-143">Both C-style arrays and safe arrays can be passed to .NET code from unmanaged code as either a safe array or a C-style array.</span></span> <span data-ttu-id="a598f-144">次の表に、アンマネージ型の値とインポートされた型を示します。</span><span class="sxs-lookup"><span data-stu-id="a598f-144">The following table shows the unmanaged type value and the imported type.</span></span>  
  
|<span data-ttu-id="a598f-145">アンマネージ型</span><span class="sxs-lookup"><span data-stu-id="a598f-145">Unmanaged type</span></span>|<span data-ttu-id="a598f-146">インポートされた型</span><span class="sxs-lookup"><span data-stu-id="a598f-146">Imported type</span></span>|  
|--------------------|-------------------|  
|<span data-ttu-id="a598f-147">**SafeArray(** *Type* **)**</span><span class="sxs-lookup"><span data-stu-id="a598f-147">**SafeArray(** *Type* **)**</span></span>|<span data-ttu-id="a598f-148">**ELEMENT_TYPE_SZARRAY** **\<** *ConvertedType* **>**</span><span class="sxs-lookup"><span data-stu-id="a598f-148">**ELEMENT_TYPE_SZARRAY** **\<** *ConvertedType* **>**</span></span><br /><br /> <span data-ttu-id="a598f-149">ランク = 1、下限 = 0。</span><span class="sxs-lookup"><span data-stu-id="a598f-149">Rank = 1, lower bound = 0.</span></span> <span data-ttu-id="a598f-150">サイズはマネージド シグネチャで指定された場合にのみ判明します。</span><span class="sxs-lookup"><span data-stu-id="a598f-150">Size is known only if provided in the managed signature.</span></span> <span data-ttu-id="a598f-151">ランク = 1 または下限 = 0 ではないセーフ配列は、**SZARRAY** としてマーシャリングできません。</span><span class="sxs-lookup"><span data-stu-id="a598f-151">Safe arrays that are not rank = 1 or lower bound = 0 cannot be marshaled as **SZARRAY**.</span></span>|  
|<span data-ttu-id="a598f-152">*Type*  **[]**</span><span class="sxs-lookup"><span data-stu-id="a598f-152">*Type*  **[]**</span></span>|<span data-ttu-id="a598f-153">**ELEMENT_TYPE_SZARRAY** **\<** *ConvertedType* **>**</span><span class="sxs-lookup"><span data-stu-id="a598f-153">**ELEMENT_TYPE_SZARRAY** **\<** *ConvertedType* **>**</span></span><br /><br /> <span data-ttu-id="a598f-154">ランク = 1、下限 = 0。</span><span class="sxs-lookup"><span data-stu-id="a598f-154">Rank = 1, lower bound = 0.</span></span> <span data-ttu-id="a598f-155">サイズはマネージド シグネチャで指定された場合にのみ判明します。</span><span class="sxs-lookup"><span data-stu-id="a598f-155">Size is known only if provided in the managed signature.</span></span>|  
  
### <a name="safe-arrays"></a><span data-ttu-id="a598f-156">セーフ配列</span><span class="sxs-lookup"><span data-stu-id="a598f-156">Safe Arrays</span></span>  
 <span data-ttu-id="a598f-157">セーフ配列がタイプ ライブラリから .NET アセンブリにインポートされるときに、配列は既知の型 (**int** など) の 1 次元配列に変換されます。</span><span class="sxs-lookup"><span data-stu-id="a598f-157">When a safe array is imported from a type library to a .NET assembly, the array is converted to a one-dimensional array of a known type (such as **int**).</span></span> <span data-ttu-id="a598f-158">パラメーターに適用される同じ型変換規則は、配列要素にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="a598f-158">The same type conversion rules that apply to parameters also apply to array elements.</span></span> <span data-ttu-id="a598f-159">たとえば、**BSTR** 型のセーフ配列は文字列のマネージド配列になり、バリアントのセーフ配列はオブジェクトのマネージド配列になります。</span><span class="sxs-lookup"><span data-stu-id="a598f-159">For example, a safe array of **BSTR** types becomes a managed array of strings and a safe array of variants becomes a managed array of objects.</span></span> <span data-ttu-id="a598f-160">**SAFEARRAY** 要素型はタイプ ライブラリからキャプチャされ、<xref:System.Runtime.InteropServices.UnmanagedType> 列挙型の **SAFEARRAY** 値に保存されます。</span><span class="sxs-lookup"><span data-stu-id="a598f-160">The **SAFEARRAY** element type is captured from the type library and saved in the **SAFEARRAY** value of the <xref:System.Runtime.InteropServices.UnmanagedType> enumeration.</span></span>  
  
 <span data-ttu-id="a598f-161">セーフ配列のランクと境界はタイプ ライブラリからは判断できないため、ランクは 1 に等しく下限は 0 に等しいと見なされます。</span><span class="sxs-lookup"><span data-stu-id="a598f-161">Because the rank and bounds of the safe array cannot be determined from the type library, the rank is assumed to equal 1 and the lower bound is assumed to equal 0.</span></span> <span data-ttu-id="a598f-162">ランクと境界は、[タイプ ライブラリ インポーター (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md) によって生成されるマネージド シグネチャで定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a598f-162">The rank and bounds must be defined in the managed signature produced by the [Type Library Importer (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md).</span></span> <span data-ttu-id="a598f-163">実行時にメソッドに渡されるランクが異なる場合、<xref:System.Runtime.InteropServices.SafeArrayRankMismatchException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="a598f-163">If the rank passed to the method at run time differs, a <xref:System.Runtime.InteropServices.SafeArrayRankMismatchException> is thrown.</span></span> <span data-ttu-id="a598f-164">実行時に渡される配列の型が異なる場合、<xref:System.Runtime.InteropServices.SafeArrayTypeMismatchException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="a598f-164">If the type of the array passed at run time differs, a <xref:System.Runtime.InteropServices.SafeArrayTypeMismatchException> is thrown.</span></span> <span data-ttu-id="a598f-165">次の例は、マネージド コードとアンマネージド コードでのセーフ配列を示しています。</span><span class="sxs-lookup"><span data-stu-id="a598f-165">The following example shows safe arrays in managed and unmanaged code.</span></span>  
  
 <span data-ttu-id="a598f-166">**アンマネージ シグネチャ**</span><span class="sxs-lookup"><span data-stu-id="a598f-166">**Unmanaged signature**</span></span>  
  
```cpp
HRESULT New1([in] SAFEARRAY( int ) ar);  
HRESULT New2([in] SAFEARRAY( DATE ) ar);  
HRESULT New3([in, out] SAFEARRAY( BSTR ) *ar);  
```  
  
 <span data-ttu-id="a598f-167">**マネージド シグネチャ**</span><span class="sxs-lookup"><span data-stu-id="a598f-167">**Managed signature**</span></span>  
  
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
  
 <span data-ttu-id="a598f-168">多次元配列 (0 以外の値にバインドされたセーフ配列) は、Tlbimp.exe によって生成されたメソッド シグネチャが、**ELEMENT_TYPE_SZARRAY** ではなく **ELEMENT_TYPE_ARRAY** の要素型を示すように変更された場合に、マネージド コードにマーシャリングできます。</span><span class="sxs-lookup"><span data-stu-id="a598f-168">Multidimensional, or nonzero-bound safe arrays, can be marshaled into managed code if the method signature produced by Tlbimp.exe is modified to indicate an element type of **ELEMENT_TYPE_ARRAY** instead of **ELEMENT_TYPE_SZARRAY**.</span></span> <span data-ttu-id="a598f-169">または、Tlbimp.exe で **/sysarray** スイッチを使用してすべての配列を <xref:System.Array?displayProperty=nameWithType> オブジェクトとしてインポートできます。</span><span class="sxs-lookup"><span data-stu-id="a598f-169">Alternatively, you can use the **/sysarray** switch with Tlbimp.exe to import all arrays as <xref:System.Array?displayProperty=nameWithType> objects.</span></span> <span data-ttu-id="a598f-170">渡される配列が多次元配列だとわかっている場合は、Tlbimp.exe で生成された Microsoft Intermediate Language (MSIL) コードを編集してから再コンパイルすることができます。</span><span class="sxs-lookup"><span data-stu-id="a598f-170">In cases where the array being passed is known to be multidimensional, you can edit the Microsoft intermediate language (MSIL) code produced by Tlbimp.exe and then recompile it.</span></span> <span data-ttu-id="a598f-171">MSIL コードの変更方法の詳細については、「[Customizing Runtime Callable Wrappers](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100))」(ランタイム呼び出し可能ラッパーのカスタマイズ) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a598f-171">For details about how to modify MSIL code, see [Customizing Runtime Callable Wrappers](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100)).</span></span>  
  
### <a name="c-style-arrays"></a><span data-ttu-id="a598f-172">C スタイル配列</span><span class="sxs-lookup"><span data-stu-id="a598f-172">C-Style Arrays</span></span>  
 <span data-ttu-id="a598f-173">C スタイル配列がタイプ ライブラリから .NET アセンブリにインポートされると、その配列は **ELEMENT_TYPE_SZARRAY** に変換されます。</span><span class="sxs-lookup"><span data-stu-id="a598f-173">When a C-style array is imported from a type library to a .NET assembly, the array is converted to **ELEMENT_TYPE_SZARRAY**.</span></span>  
  
 <span data-ttu-id="a598f-174">配列要素型は、タイプ ライブラリから決定され、インポート中は保持されます。</span><span class="sxs-lookup"><span data-stu-id="a598f-174">The array element type is determined from the type library and preserved during the import.</span></span> <span data-ttu-id="a598f-175">パラメーターに適用される同じ変換規則は、配列の要素にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="a598f-175">The same conversion rules that apply to parameters also apply to array elements.</span></span> <span data-ttu-id="a598f-176">たとえば、**LPStr** 型の配列は、**String** 型の配列になります。</span><span class="sxs-lookup"><span data-stu-id="a598f-176">For example, an array of **LPStr** types becomes an array of **String** types.</span></span> <span data-ttu-id="a598f-177">Tlbimp.exe は配列要素型をキャプチャし、<xref:System.Runtime.InteropServices.MarshalAsAttribute> 属性をパラメーターに適用します。</span><span class="sxs-lookup"><span data-stu-id="a598f-177">Tlbimp.exe captures the array element type and applies the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute to the parameter.</span></span>  
  
 <span data-ttu-id="a598f-178">配列ランクは 1 と等しいと見なされます。</span><span class="sxs-lookup"><span data-stu-id="a598f-178">The array rank is assumed to equal 1.</span></span> <span data-ttu-id="a598f-179">ランクが 1 より大きい場合、配列は 1 次元配列として列優先順でマーシャリングされます。</span><span class="sxs-lookup"><span data-stu-id="a598f-179">If the rank is greater than 1, the array is marshaled as a one-dimensional array in column-major order.</span></span> <span data-ttu-id="a598f-180">下限は常に = 0 です。</span><span class="sxs-lookup"><span data-stu-id="a598f-180">The lower bound always equals 0.</span></span>  
  
 <span data-ttu-id="a598f-181">タイプ ライブラリには、固定長または可変長の配列を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="a598f-181">Type libraries can contain arrays of fixed or variable length.</span></span> <span data-ttu-id="a598f-182">Tlbimp.exe は、タイプ ライブラリから固定長配列のみをインポートできます。これは、タイプ ライブラリに可変長配列をマーシャリングするために必要な情報が不足しているためです。</span><span class="sxs-lookup"><span data-stu-id="a598f-182">Tlbimp.exe can import only fixed-length arrays from type libraries because type libraries lack the information needed to marshal variable-length arrays.</span></span> <span data-ttu-id="a598f-183">固定長配列では、サイズはタイプ ライブラリからインポートされ、パラメーターに適用される **MarshalAsAttribute** でキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="a598f-183">With fixed-length arrays, the size is imported from the type library and captured in the **MarshalAsAttribute** that is applied to the parameter.</span></span>  
  
 <span data-ttu-id="a598f-184">次の例に示すように、可変長配列を含むタイプ ライブラリを手動で定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a598f-184">You must manually define type libraries containing variable-length arrays, as shown in the following example.</span></span>  
  
 <span data-ttu-id="a598f-185">**アンマネージ シグネチャ**</span><span class="sxs-lookup"><span data-stu-id="a598f-185">**Unmanaged signature**</span></span>  
  
```cpp
HRESULT New1(int ar[10]);  
HRESULT New2(double ar[10][20]);  
HRESULT New3(LPWStr ar[10]);  
```  
  
 <span data-ttu-id="a598f-186">**マネージド シグネチャ**</span><span class="sxs-lookup"><span data-stu-id="a598f-186">**Managed signature**</span></span>  
  
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
  
 <span data-ttu-id="a598f-187">インターフェイス定義言語 (IDL) ソース内の配列に **size_is** 属性または **length_is** 属性を適用してサイズをクライアントに伝達することができますが、Microsoft インターフェイス定義言語 (MIDL) コンパイラはその情報をタイプ ライブラリに伝達しません。</span><span class="sxs-lookup"><span data-stu-id="a598f-187">Although you can apply the **size_is** or **length_is** attributes to an array in Interface Definition Language (IDL) source to convey the size to a client, the Microsoft Interface Definition Language (MIDL) compiler does not propagate that information to the type library.</span></span> <span data-ttu-id="a598f-188">サイズがわからないと、相互運用マーシャリング サービスが配列要素をマーシャリングできません。</span><span class="sxs-lookup"><span data-stu-id="a598f-188">Without knowing the size, the interop marshaling service cannot marshal the array elements.</span></span> <span data-ttu-id="a598f-189">その結果、可変長配列は参照引数としてインポートされます。</span><span class="sxs-lookup"><span data-stu-id="a598f-189">Consequently, variable-length arrays are imported as reference arguments.</span></span> <span data-ttu-id="a598f-190">(例:</span><span class="sxs-lookup"><span data-stu-id="a598f-190">For example:</span></span>  
  
 <span data-ttu-id="a598f-191">**アンマネージ シグネチャ**</span><span class="sxs-lookup"><span data-stu-id="a598f-191">**Unmanaged signature**</span></span>  
  
```cpp
HRESULT New1(int ar[]);  
HRESULT New2(int ArSize, [size_is(ArSize)] double ar[]);  
HRESULT New3(int ElemCnt, [length_is(ElemCnt)] LPStr ar[]);  
```  
  
 <span data-ttu-id="a598f-192">**マネージド シグネチャ**</span><span class="sxs-lookup"><span data-stu-id="a598f-192">**Managed signature**</span></span>  
  
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
  
 <span data-ttu-id="a598f-193">Tlbimp.exe によって生成された Microsoft Intermediate Language (MSIL) コードを編集して、マーシャラーに配列サイズを提供してから再コンパイルすることができます。</span><span class="sxs-lookup"><span data-stu-id="a598f-193">You can provide the marshaler with the array size by editing the Microsoft intermediate language (MSIL) code produced by Tlbimp.exe and then recompiling it.</span></span> <span data-ttu-id="a598f-194">MSIL コードの変更方法の詳細については、「[Customizing Runtime Callable Wrappers](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100))」(ランタイム呼び出し可能ラッパーのカスタマイズ) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a598f-194">For details about how to modify MSIL code, see [Customizing Runtime Callable Wrappers](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100)).</span></span> <span data-ttu-id="a598f-195">配列内の要素の数を示すには、次の方法のいずれかの方法で、<xref:System.Runtime.InteropServices.MarshalAsAttribute> 型をマネージド メソッド定義の配列パラメーターに適用します。</span><span class="sxs-lookup"><span data-stu-id="a598f-195">To indicate the number of elements in the array, apply the <xref:System.Runtime.InteropServices.MarshalAsAttribute> type to the array parameter of the managed method definition in one of the following ways:</span></span>  
  
- <span data-ttu-id="a598f-196">配列内の要素数を含む別のパラメーターを特定します。</span><span class="sxs-lookup"><span data-stu-id="a598f-196">Identify another parameter that contains the number of elements in the array.</span></span> <span data-ttu-id="a598f-197">パラメーターは位置によって識別され、最初のパラメーターは番号 0 から始まります。</span><span class="sxs-lookup"><span data-stu-id="a598f-197">The parameters are identified by position, starting with the first parameter as number 0.</span></span>     
  
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
  
- <span data-ttu-id="a598f-198">配列のサイズを定数として定義します。</span><span class="sxs-lookup"><span data-stu-id="a598f-198">Define the size of the array as a constant.</span></span> <span data-ttu-id="a598f-199">(例:</span><span class="sxs-lookup"><span data-stu-id="a598f-199">For example:</span></span>  
  
    ```vb  
    Sub [New](\<MarshalAs(UnmanagedType.LPArray, SizeConst:=128)> _  
       ar() As Integer)  
    ```  
  
    ```csharp  
    void New(  
       [MarshalAs(UnmanagedType.LPArray, SizeConst=128)] int[] ar );  
    ```  
  
 <span data-ttu-id="a598f-200">アンマネージド コードからマネージド コードに配列をマーシャリングする場合、マーシャラーはパラメーターに関連付けられた **MarshalAsAttribute** をチェックして配列サイズを決定します。</span><span class="sxs-lookup"><span data-stu-id="a598f-200">When marshaling arrays from unmanaged code to managed code, the marshaler checks the **MarshalAsAttribute** associated with the parameter to determine the array size.</span></span> <span data-ttu-id="a598f-201">配列サイズが指定されていない場合は、1 つの要素のみがマーシャリングされます。</span><span class="sxs-lookup"><span data-stu-id="a598f-201">If the array size is not specified, only one element is marshaled.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a598f-202">**MarshalAsAttribute** は、マネージド配列のアンマネージド コードへのマーシャリングには影響しません。</span><span class="sxs-lookup"><span data-stu-id="a598f-202">The **MarshalAsAttribute** has no effect on marshaling managed arrays to unmanaged code.</span></span> <span data-ttu-id="a598f-203">その方向では、配列サイズは検査で決定されます。</span><span class="sxs-lookup"><span data-stu-id="a598f-203">In that direction, the array size is determined by examination.</span></span> <span data-ttu-id="a598f-204">マネージド配列のサブセットをマーシャリングする方法はありません。</span><span class="sxs-lookup"><span data-stu-id="a598f-204">There is no way to marshal a subset of a managed array.</span></span>  
  
 <span data-ttu-id="a598f-205">相互運用マーシャラーは、**CoTaskMemAlloc** メソッドと **CoTaskMemFree** メソッドを使用してメモリの割り当てと取得を行います。</span><span class="sxs-lookup"><span data-stu-id="a598f-205">The interop marshaler uses the **CoTaskMemAlloc** and **CoTaskMemFree** methods to allocate and retrieve memory.</span></span> <span data-ttu-id="a598f-206">アンマネージ コードによって実行されるメモリの割り当てでは、これらのメソッドも使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a598f-206">Memory allocation performed by unmanaged code must also use these methods.</span></span>  
  
## <a name="passing-arrays-to-com"></a><span data-ttu-id="a598f-207">COM への配列の引き渡し</span><span class="sxs-lookup"><span data-stu-id="a598f-207">Passing Arrays to COM</span></span>  
 <span data-ttu-id="a598f-208">すべてのマネージド配列型は、マネージド コードからアンマネージド コードに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="a598f-208">All managed array types can be passed to unmanaged code from managed code.</span></span> <span data-ttu-id="a598f-209">次の表に示すように、マネージド型とそれに適用される属性に応じて、セーフ配列または C スタイル配列として配列にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="a598f-209">Depending on the managed type and the attributes applied to it, the array can be accessed as a safe array or a C-style array, as shown in the following table.</span></span>  
  
|<span data-ttu-id="a598f-210">マネージド配列型</span><span class="sxs-lookup"><span data-stu-id="a598f-210">Managed array type</span></span>|<span data-ttu-id="a598f-211">エクスポート</span><span class="sxs-lookup"><span data-stu-id="a598f-211">Exported as</span></span>|  
|------------------------|-----------------|  
|<span data-ttu-id="a598f-212">**ELEMENT_TYPE_SZARRAY** **\<** *type* **>**</span><span class="sxs-lookup"><span data-stu-id="a598f-212">**ELEMENT_TYPE_SZARRAY** **\<** *type* **>**</span></span>|<span data-ttu-id="a598f-213"><xref:System.Runtime.InteropServices.UnmanagedType> **.SafeArray(** *type* **)**</span><span class="sxs-lookup"><span data-stu-id="a598f-213"><xref:System.Runtime.InteropServices.UnmanagedType> **.SafeArray(** *type* **)**</span></span><br /><br /> <span data-ttu-id="a598f-214">**UnmanagedType.LPArray**</span><span class="sxs-lookup"><span data-stu-id="a598f-214">**UnmanagedType.LPArray**</span></span><br /><br /> <span data-ttu-id="a598f-215">型はシグネチャで提供されます。</span><span class="sxs-lookup"><span data-stu-id="a598f-215">Type is provided in the signature.</span></span> <span data-ttu-id="a598f-216">ランクは常に 1 で、下限は常に 0 です。</span><span class="sxs-lookup"><span data-stu-id="a598f-216">Rank is always 1, lower bound is always 0.</span></span> <span data-ttu-id="a598f-217">サイズは実行時に常に把握されています。</span><span class="sxs-lookup"><span data-stu-id="a598f-217">Size is always known at run time.</span></span>|  
|<span data-ttu-id="a598f-218">**ELEMENT_TYPE_ARRAY** **\<** *type* **>** **\<** *rank* **>** [ **\<** *bounds* **>** ]</span><span class="sxs-lookup"><span data-stu-id="a598f-218">**ELEMENT_TYPE_ARRAY** **\<** *type* **>** **\<** *rank* **>**[**\<** *bounds* **>**]</span></span>|<span data-ttu-id="a598f-219">**UnmanagedType.SafeArray(** *type* **)**</span><span class="sxs-lookup"><span data-stu-id="a598f-219">**UnmanagedType.SafeArray(** *type* **)**</span></span><br /><br /> <span data-ttu-id="a598f-220">**UnmanagedType.LPArray**</span><span class="sxs-lookup"><span data-stu-id="a598f-220">**UnmanagedType.LPArray**</span></span><br /><br /> <span data-ttu-id="a598f-221">型、ランク、境界はシグネチャで提供されます。</span><span class="sxs-lookup"><span data-stu-id="a598f-221">Type, rank, bounds are provided in the signature.</span></span> <span data-ttu-id="a598f-222">サイズは実行時に常に把握されています。</span><span class="sxs-lookup"><span data-stu-id="a598f-222">Size is always known at run time.</span></span>|  
|<span data-ttu-id="a598f-223">**ELEMENT_TYPE_CLASS** **\<** <xref:System.Array?displayProperty=nameWithType> **>**</span><span class="sxs-lookup"><span data-stu-id="a598f-223">**ELEMENT_TYPE_CLASS** **\<**<xref:System.Array?displayProperty=nameWithType>**>**</span></span>|<span data-ttu-id="a598f-224">**UT_Interface**</span><span class="sxs-lookup"><span data-stu-id="a598f-224">**UT_Interface**</span></span><br /><br /> <span data-ttu-id="a598f-225">**UnmanagedType.SafeArray(** *type* **)**</span><span class="sxs-lookup"><span data-stu-id="a598f-225">**UnmanagedType.SafeArray(** *type* **)**</span></span><br /><br /> <span data-ttu-id="a598f-226">型、ランク、境界、およびサイズは実行時に常に把握されています。</span><span class="sxs-lookup"><span data-stu-id="a598f-226">Type, rank, bounds, and size are always known at run time.</span></span>|  
  
 <span data-ttu-id="a598f-227">LPSTR または LPWSTR を含む構造体の配列に関連する OLE オートメーションの制限があります。</span><span class="sxs-lookup"><span data-stu-id="a598f-227">There is a limitation in OLE Automation relating to arrays of structures that contain LPSTR or LPWSTR.</span></span>  <span data-ttu-id="a598f-228">そのため、**String** フィールドは **UnmanagedType.BSTR** としてマーシャリングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a598f-228">Therefore, **String** fields have to be marshaled as **UnmanagedType.BSTR**.</span></span> <span data-ttu-id="a598f-229">この操作を行わない場合、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="a598f-229">Otherwise, an exception will be thrown.</span></span>  
  
### <a name="element_type_szarray"></a><span data-ttu-id="a598f-230">ELEMENT_TYPE_SZARRAY</span><span class="sxs-lookup"><span data-stu-id="a598f-230">ELEMENT_TYPE_SZARRAY</span></span>  
 <span data-ttu-id="a598f-231">**ELEMENT_TYPE_SZARRAY** パラメーター (1 次元配列) を含むメソッドが .NET アセンブリからタイプ ライブラリにエクスポートされるときに、配列パラメーターが特定の型の **SAFEARRAY** に変換されます。</span><span class="sxs-lookup"><span data-stu-id="a598f-231">When a method containing an **ELEMENT_TYPE_SZARRAY** parameter (one-dimensional array) is exported from a .NET assembly to a type library, the array parameter is converted to a **SAFEARRAY** of a given type.</span></span> <span data-ttu-id="a598f-232">同じ変換規則が配列要素型に適用されます。</span><span class="sxs-lookup"><span data-stu-id="a598f-232">The same conversion rules apply to the array element types.</span></span> <span data-ttu-id="a598f-233">マネージド配列の内容はマネージド メモリから **SAFEARRAY** に自動的にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="a598f-233">The contents of the managed array are automatically copied from managed memory into the **SAFEARRAY**.</span></span> <span data-ttu-id="a598f-234">(例:</span><span class="sxs-lookup"><span data-stu-id="a598f-234">For example:</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="a598f-235">マネージド シグネチャ</span><span class="sxs-lookup"><span data-stu-id="a598f-235">Managed signature</span></span>  
  
```vb  
Sub [New](ar() As Long)  
Sub [New](ar() As String)  
```  
  
```csharp  
void New(long[] ar );  
void New(String[] ar );  
```  
  
#### <a name="unmanaged-signature"></a><span data-ttu-id="a598f-236">アンマネージ シグネチャ</span><span class="sxs-lookup"><span data-stu-id="a598f-236">Unmanaged signature</span></span>  
  
```cpp
HRESULT New([in] SAFEARRAY( long ) ar);
HRESULT New([in] SAFEARRAY( BSTR ) ar);  
```  
  
 <span data-ttu-id="a598f-237">セーフ配列のランクは常に 1 で、下限は常に 0 です。</span><span class="sxs-lookup"><span data-stu-id="a598f-237">The rank of the safe arrays is always 1 and the lower bound is always 0.</span></span> <span data-ttu-id="a598f-238">サイズは実行時に渡されるマネージド配列のサイズによって決まります。</span><span class="sxs-lookup"><span data-stu-id="a598f-238">The size is determined at run time by the size of the managed array being passed.</span></span>  
  
 <span data-ttu-id="a598f-239"><xref:System.Runtime.InteropServices.MarshalAsAttribute> 属性を使用することで、配列を C スタイル配列としてマーシャリングすることもできます。</span><span class="sxs-lookup"><span data-stu-id="a598f-239">The array can also be marshaled as a C-style array by using the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute.</span></span> <span data-ttu-id="a598f-240">(例:</span><span class="sxs-lookup"><span data-stu-id="a598f-240">For example:</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="a598f-241">マネージド シグネチャ</span><span class="sxs-lookup"><span data-stu-id="a598f-241">Managed signature</span></span>  
  
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
  
#### <a name="unmanaged-signature"></a><span data-ttu-id="a598f-242">アンマネージ シグネチャ</span><span class="sxs-lookup"><span data-stu-id="a598f-242">Unmanaged signature</span></span>  
  
```cpp
HRESULT New(long ar[]);
HRESULT New(BSTR ar[]);
HRESULT New(LPStr ar[]);  
```  
  
 <span data-ttu-id="a598f-243">マーシャラーには配列をマーシャリングするために必要な長さ情報がありますが、配列の長さは通常、呼び出し先に長さを伝えるために個別の引数として渡されます。</span><span class="sxs-lookup"><span data-stu-id="a598f-243">Although the marshaler has the length information needed to marshal the array, the array length is usually passed as a separate argument to convey the length to the callee.</span></span>  
  
### <a name="element_type_array"></a><span data-ttu-id="a598f-244">ELEMENT_TYPE_ARRAY</span><span class="sxs-lookup"><span data-stu-id="a598f-244">ELEMENT_TYPE_ARRAY</span></span>  
 <span data-ttu-id="a598f-245">**ELEMENT_TYPE_ARRAY** パラメーターを含むメソッドが .NET アセンブリからタイプ ライブラリにエクスポートされるときに、配列パラメーターが特定の型の **SAFEARRAY** に変換されます。</span><span class="sxs-lookup"><span data-stu-id="a598f-245">When a method containing an **ELEMENT_TYPE_ARRAY** parameter is exported from a .NET assembly to a type library, the array parameter is converted to a **SAFEARRAY** of a given type.</span></span> <span data-ttu-id="a598f-246">マネージド配列の内容はマネージド メモリから **SAFEARRAY** に自動的にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="a598f-246">The contents of the managed array are automatically copied from managed memory into the **SAFEARRAY**.</span></span> <span data-ttu-id="a598f-247">(例:</span><span class="sxs-lookup"><span data-stu-id="a598f-247">For example:</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="a598f-248">マネージド シグネチャ</span><span class="sxs-lookup"><span data-stu-id="a598f-248">Managed signature</span></span>  
  
```vb  
Sub [New](ar(,) As Long)  
Sub [New](ar(,) As String)  
```  
  
```csharp  
void New( long [,] ar );  
void New( String [,] ar );  
```  
  
#### <a name="unmanaged-signature"></a><span data-ttu-id="a598f-249">アンマネージ シグネチャ</span><span class="sxs-lookup"><span data-stu-id="a598f-249">Unmanaged signature</span></span>  
  
```cpp
HRESULT New([in] SAFEARRAY( long ) ar);
HRESULT New([in] SAFEARRAY( BSTR ) ar);  
```  
  
 <span data-ttu-id="a598f-250">セーフ配列のランク、サイズ、およ境界は、マネージド配列の特性によって実行時に決定されます。</span><span class="sxs-lookup"><span data-stu-id="a598f-250">The rank, size, and bounds of the safe arrays are determined at run time by the characteristics of the managed array.</span></span>  
  
 <span data-ttu-id="a598f-251"><xref:System.Runtime.InteropServices.MarshalAsAttribute> 属性を適用することで、配列を C スタイル配列としてマーシャリングすることもできます。</span><span class="sxs-lookup"><span data-stu-id="a598f-251">The array can also be marshaled as a C-style array by applying the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute.</span></span> <span data-ttu-id="a598f-252">(例:</span><span class="sxs-lookup"><span data-stu-id="a598f-252">For example:</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="a598f-253">マネージド シグネチャ</span><span class="sxs-lookup"><span data-stu-id="a598f-253">Managed signature</span></span>  
  
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
  
#### <a name="unmanaged-signature"></a><span data-ttu-id="a598f-254">アンマネージ シグネチャ</span><span class="sxs-lookup"><span data-stu-id="a598f-254">Unmanaged signature</span></span>  
  
```cpp
HRESULT New(long ar[]);
HRESULT New(LPStr ar[]);  
```  
  
 <span data-ttu-id="a598f-255">入れ子にされた配列をマーシャリングすることはできません。</span><span class="sxs-lookup"><span data-stu-id="a598f-255">Nested arrays cannot be marshaled.</span></span> <span data-ttu-id="a598f-256">たとえば、次のシグネチャを[タイプ ライブラリ エクスポーター (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md) を使用してエクスポートすると、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="a598f-256">For example, the following signature generates an error when exported with the [Type Library Exporter (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md).</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="a598f-257">マネージド シグネチャ</span><span class="sxs-lookup"><span data-stu-id="a598f-257">Managed signature</span></span>  
  
```vb  
Sub [New](ar()()() As Long)  
```  
  
```csharp  
void New(long [][][] ar );  
```  
  
### <a name="element_type_class-systemarray"></a><span data-ttu-id="a598f-258">ELEMENT_TYPE_CLASS \<System.Array></span><span class="sxs-lookup"><span data-stu-id="a598f-258">ELEMENT_TYPE_CLASS \<System.Array></span></span>  
 <span data-ttu-id="a598f-259"><xref:System.Array?displayProperty=nameWithType> パラメーターを含むメソッドが .NET アセンブリからタイプ ライブラリにエクスポートされるときに、配列パラメーターが特定の型の **_Array** インターフェイスに変換されます。</span><span class="sxs-lookup"><span data-stu-id="a598f-259">When a method containing a <xref:System.Array?displayProperty=nameWithType> parameter is exported from a .NET assembly to a type library, the array parameter is converted to an **_Array** interface.</span></span> <span data-ttu-id="a598f-260">マネージド配列の内容には、 **_Array** インターフェイスのメソッドとプロパティを介してのみアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="a598f-260">The contents of the managed array are accessible only through the methods and properties of the **_Array** interface.</span></span> <span data-ttu-id="a598f-261"><xref:System.Runtime.InteropServices.MarshalAsAttribute> 属性を使用することで、**System.Array** を **SAFEARRAY** としてマーシャリングすることもできます。</span><span class="sxs-lookup"><span data-stu-id="a598f-261">**System.Array** can also be marshaled as a **SAFEARRAY** by using the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute.</span></span> <span data-ttu-id="a598f-262">セーフ配列としてマーシャリングすると、配列要素はバリアントとしてマーシャリングされます。</span><span class="sxs-lookup"><span data-stu-id="a598f-262">When marshaled as a safe array, the array elements are marshaled as variants.</span></span> <span data-ttu-id="a598f-263">(例:</span><span class="sxs-lookup"><span data-stu-id="a598f-263">For example:</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="a598f-264">マネージド シグネチャ</span><span class="sxs-lookup"><span data-stu-id="a598f-264">Managed signature</span></span>  
  
```vb  
Sub New1( ar As System.Array )  
Sub New2( <MarshalAs(UnmanagedType.Safe array)> ar As System.Array )  
```  
  
```csharp  
void New1( System.Array ar );  
void New2( [MarshalAs(UnmanagedType.Safe array)] System.Array ar );  
```  
  
#### <a name="unmanaged-signature"></a><span data-ttu-id="a598f-265">アンマネージ シグネチャ</span><span class="sxs-lookup"><span data-stu-id="a598f-265">Unmanaged signature</span></span>  
  
```cpp
HRESULT New([in] _Array *ar);
HRESULT New([in] SAFEARRAY(VARIANT) ar);  
```  
  
### <a name="arrays-within-structures"></a><span data-ttu-id="a598f-266">構造体内の配列</span><span class="sxs-lookup"><span data-stu-id="a598f-266">Arrays within Structures</span></span>  
 <span data-ttu-id="a598f-267">アンマネージ構造体には、埋め込まれた配列を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="a598f-267">Unmanaged structures can contain embedded arrays.</span></span> <span data-ttu-id="a598f-268">既定では、これらの埋め込まれた配列フィールドは SAFEARRAY としてマーシャリングされます。</span><span class="sxs-lookup"><span data-stu-id="a598f-268">By default, these embedded array fields are marshaled as a SAFEARRAY.</span></span> <span data-ttu-id="a598f-269">次の例では、`s1` が構造体そのものに直接割り当てられている埋め込まれた配列です。</span><span class="sxs-lookup"><span data-stu-id="a598f-269">In the following example, `s1` is an embedded array that is allocated directly within the structure itself.</span></span>  
  
#### <a name="unmanaged-representation"></a><span data-ttu-id="a598f-270">アンマネージ表現</span><span class="sxs-lookup"><span data-stu-id="a598f-270">Unmanaged representation</span></span>  
  
```cpp
struct MyStruct {  
    short s1[128];  
}  
```  
  
 <span data-ttu-id="a598f-271"><xref:System.Runtime.InteropServices.UnmanagedType> としてマーシャリングできる配列で、<xref:System.Runtime.InteropServices.MarshalAsAttribute> フィールドを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a598f-271">Arrays can be marshaled as <xref:System.Runtime.InteropServices.UnmanagedType>, which requires you to set the <xref:System.Runtime.InteropServices.MarshalAsAttribute> field.</span></span> <span data-ttu-id="a598f-272">サイズは定数としてのみ設定できます。</span><span class="sxs-lookup"><span data-stu-id="a598f-272">The size can be set only as a constant.</span></span> <span data-ttu-id="a598f-273">次のコードは、`MyStruct` の対応するマネージド定義を示しています。</span><span class="sxs-lookup"><span data-stu-id="a598f-273">The following code shows the corresponding managed definition of `MyStruct`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a598f-274">関連項目</span><span class="sxs-lookup"><span data-stu-id="a598f-274">See also</span></span>

- [<span data-ttu-id="a598f-275">既定のマーシャリング動作</span><span class="sxs-lookup"><span data-stu-id="a598f-275">Default Marshaling Behavior</span></span>](default-marshaling-behavior.md)
- [<span data-ttu-id="a598f-276">Blittable 型と非 Blittable 型</span><span class="sxs-lookup"><span data-stu-id="a598f-276">Blittable and Non-Blittable Types</span></span>](blittable-and-non-blittable-types.md)
- <span data-ttu-id="a598f-277">[方向属性](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a598f-277">[Directional Attributes](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100))</span></span>
- [<span data-ttu-id="a598f-278">コピーと固定</span><span class="sxs-lookup"><span data-stu-id="a598f-278">Copying and Pinning</span></span>](copying-and-pinning.md)
