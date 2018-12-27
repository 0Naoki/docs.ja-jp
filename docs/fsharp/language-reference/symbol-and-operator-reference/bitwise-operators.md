---
title: ビット処理演算子
description: 使用可能なビットごとの演算子について説明します、F#プログラミング言語。
ms.date: 07/20/2018
ms.openlocfilehash: 01c68be485525b49eb3121dfaea6dce0adfe3972
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2018
ms.locfileid: "53611972"
---
# <a name="bitwise-operators"></a><span data-ttu-id="8c882-103">ビット処理演算子</span><span class="sxs-lookup"><span data-stu-id="8c882-103">Bitwise Operators</span></span>

<span data-ttu-id="8c882-104">このトピックでは、F# 言語で使用可能なビットごとの演算子について説明します。</span><span class="sxs-lookup"><span data-stu-id="8c882-104">This topic describes bitwise operators that are available in the F# language.</span></span>

## <a name="summary-of-bitwise-operators"></a><span data-ttu-id="8c882-105">ビットごとの演算子の概要</span><span class="sxs-lookup"><span data-stu-id="8c882-105">Summary of Bitwise Operators</span></span>

<span data-ttu-id="8c882-106">次の表では、ボックス化解除された整数型の F# 言語でサポートされているビットごとの演算子について説明します。</span><span class="sxs-lookup"><span data-stu-id="8c882-106">The following table describes the bitwise operators that are supported for unboxed integral types in the F# language.</span></span>

|<span data-ttu-id="8c882-107">演算子</span><span class="sxs-lookup"><span data-stu-id="8c882-107">Operator</span></span>|<span data-ttu-id="8c882-108">メモ</span><span class="sxs-lookup"><span data-stu-id="8c882-108">Notes</span></span>|
|--------|-----|
|`&&&`|<span data-ttu-id="8c882-109">ビットごとの AND 演算子です。</span><span class="sxs-lookup"><span data-stu-id="8c882-109">Bitwise AND operator.</span></span> <span data-ttu-id="8c882-110">結果のビットは、両方のソース オペランドの対応するビットが 1 の場合にのみ、値 1 を持ちます。</span><span class="sxs-lookup"><span data-stu-id="8c882-110">Bits in the result have the value 1 if and only if the corresponding bits in both source operands are 1.</span></span>|
|<code>&#124;&#124;&#124;</code>|<span data-ttu-id="8c882-111">ビットごとの OR 演算子。</span><span class="sxs-lookup"><span data-stu-id="8c882-111">Bitwise OR operator.</span></span> <span data-ttu-id="8c882-112">結果のビットは、いずれかに値 1 を持つソースに対応するビットのオペランドには 1 です。</span><span class="sxs-lookup"><span data-stu-id="8c882-112">Bits in the result have the value 1 if either of the corresponding bits in the source operands are 1.</span></span>|
|`^^^`|<span data-ttu-id="8c882-113">ビットごとの排他的 OR 演算子。</span><span class="sxs-lookup"><span data-stu-id="8c882-113">Bitwise exclusive OR operator.</span></span> <span data-ttu-id="8c882-114">結果のビットは、ソース オペランドのビットがある値が等しくない場合にのみ、値 1 を持ちます。</span><span class="sxs-lookup"><span data-stu-id="8c882-114">Bits in the result have the value 1 if and only if bits in the source operands have unequal values.</span></span>|
|`~~~`|<span data-ttu-id="8c882-115">ビットごとの否定演算子。</span><span class="sxs-lookup"><span data-stu-id="8c882-115">Bitwise negation operator.</span></span> <span data-ttu-id="8c882-116">これは単項演算子であり、結果はソース オペランド内のすべての 0 ビットが 1 のビットに変換し、すべての 1 ビットが 0 のビットに変換されます。</span><span class="sxs-lookup"><span data-stu-id="8c882-116">This is a unary operator and produces a result in which all 0 bits in the source operand are converted to 1 bits and all 1 bits are converted to 0 bits.</span></span>|
|`<<<`|<span data-ttu-id="8c882-117">ビットごとの左シフト演算子。</span><span class="sxs-lookup"><span data-stu-id="8c882-117">Bitwise left-shift operator.</span></span> <span data-ttu-id="8c882-118">最初のオペランドのビットを 2 番目のオペランドのビット数だけ左にシフトになります。</span><span class="sxs-lookup"><span data-stu-id="8c882-118">The result is the first operand with bits shifted left by the number of bits in the second operand.</span></span> <span data-ttu-id="8c882-119">最上位の位置からシフトが最下位の位置に回転していません。</span><span class="sxs-lookup"><span data-stu-id="8c882-119">Bits shifted off the most significant position are not rotated into the least significant position.</span></span> <span data-ttu-id="8c882-120">最下位ビットは 0 で埋められます。</span><span class="sxs-lookup"><span data-stu-id="8c882-120">The least significant bits are padded with zeros.</span></span> <span data-ttu-id="8c882-121">2 番目の引数の型が`int32`します。</span><span class="sxs-lookup"><span data-stu-id="8c882-121">The type of the second argument is `int32`.</span></span>|
|`>>>`|<span data-ttu-id="8c882-122">ビットごとの右シフト演算子。</span><span class="sxs-lookup"><span data-stu-id="8c882-122">Bitwise right-shift operator.</span></span> <span data-ttu-id="8c882-123">結果は、2 番目のオペランドのビット数だけ右にシフトするビットの最初のオペランドです。</span><span class="sxs-lookup"><span data-stu-id="8c882-123">The result is the first operand with bits shifted right by the number of bits in the second operand.</span></span> <span data-ttu-id="8c882-124">最下位の位置からシフトが最も重要な位置に回転していません。</span><span class="sxs-lookup"><span data-stu-id="8c882-124">Bits shifted off the least significant position are not rotated into the most significant position.</span></span> <span data-ttu-id="8c882-125">符号なしの型の最上位ビットが 0 で埋められます。</span><span class="sxs-lookup"><span data-stu-id="8c882-125">For unsigned types, the most significant bits are padded with zeros.</span></span> <span data-ttu-id="8c882-126">負の値で署名された型の場合は、最上位ビットはものに埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="8c882-126">For signed types with negative values, the most significant bits are padded with ones.</span></span> <span data-ttu-id="8c882-127">2 番目の引数の型が`int32`します。</span><span class="sxs-lookup"><span data-stu-id="8c882-127">The type of the second argument is `int32`.</span></span>|

<span data-ttu-id="8c882-128">次の種類は、ビットごとの演算子で使用できます: `byte`、 `sbyte`、 `int16`、 `uint16`、 `int32 (int)`、 `uint32`、 `int64`、 `uint64`、 `nativeint`、および`unativeint`します。</span><span class="sxs-lookup"><span data-stu-id="8c882-128">The following types can be used with bitwise operators: `byte`, `sbyte`, `int16`, `uint16`, `int32 (int)`, `uint32`, `int64`, `uint64`, `nativeint`, and `unativeint`.</span></span>

## <a name="see-also"></a><span data-ttu-id="8c882-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="8c882-129">See also</span></span>

- [<span data-ttu-id="8c882-130">シンボルと演算子のリファレンス</span><span class="sxs-lookup"><span data-stu-id="8c882-130">Symbol and Operator Reference</span></span>](index.md)
- [<span data-ttu-id="8c882-131">算術演算子</span><span class="sxs-lookup"><span data-stu-id="8c882-131">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="8c882-132">ブール演算子</span><span class="sxs-lookup"><span data-stu-id="8c882-132">Boolean Operators</span></span>](boolean-operators.md)