---
title: SqlStreamChars.Close メソッド (System.Data.SqlTypes)
author: douglaslMS
ms.author: douglasl
ms.date: 12/20/2018
ms.technology:
- dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Close
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 5b7ba05b0659bfd2cad165826469c0c8f0674797
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/11/2019
ms.locfileid: "54221168"
---
# <a name="sqlstreamcharsclose-method"></a><span data-ttu-id="25dc4-102">SqlStreamChars.Close メソッド</span><span class="sxs-lookup"><span data-stu-id="25dc4-102">SqlStreamChars.Close Method</span></span>

<span data-ttu-id="25dc4-103">現在のストリームを終了し、ストリームに関連付けられているすべてのシステム リソースを解放します。</span><span class="sxs-lookup"><span data-stu-id="25dc4-103">Closes the current stream and releases any system resources associated with the stream.</span></span> <span data-ttu-id="25dc4-104">このメソッドを含むアセンブリには、SQLAccess.dll で友人関係があります。</span><span class="sxs-lookup"><span data-stu-id="25dc4-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="25dc4-105">SQL Server で使用するものでは。</span><span class="sxs-lookup"><span data-stu-id="25dc4-105">It's intended for use by SQL Server.</span></span><span data-ttu-id="25dc4-106"> その他のデータベースには、そのデータベースによって提供されるホスティング メカニズムを使用します。</span><span class="sxs-lookup"><span data-stu-id="25dc4-106"> For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public virtual void Close ();
```

## <a name="remarks"></a><span data-ttu-id="25dc4-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="25dc4-107">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="25dc4-108">`SqlStreamChars.Close`メソッドはプライベートであり、コード内で直接使用するものではありません。</span><span class="sxs-lookup"><span data-stu-id="25dc4-108">The `SqlStreamChars.Close` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="25dc4-109">Microsoft はいかなる運用アプリケーションでこのフィールドの使用をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="25dc4-109">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="25dc4-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="25dc4-110">Requirements</span></span>

<span data-ttu-id="25dc4-111">**名前空間:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="25dc4-111">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="25dc4-112">**アセンブリ:** System.Data (system.data.dll 内)</span><span class="sxs-lookup"><span data-stu-id="25dc4-112">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="25dc4-113">**.NET framework のバージョン:** 2.0 以降で使用可能です。</span><span class="sxs-lookup"><span data-stu-id="25dc4-113">**.NET Framework versions:** Available since 2.0.</span></span>