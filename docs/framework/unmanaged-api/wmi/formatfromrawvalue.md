---
title: FormatFromRawValue 関数 (アンマネージ API リファレンス)
description: FormatFromRawValue 関数では、生のパフォーマンス データを指定された形式に変換します。
ms.date: 11/21/2017
api_name:
- FormatFromRawValue
api_location:
- PerfCounter.dll
api_type:
- DLLExport
f1_keywords:
- FormatFromRawValue
helpviewer_keywords:
- FormatFromRawValue function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 44a84b03c85cc1332c07ffbaf53187b7f01d0236
ms.sourcegitcommit: e994e47d3582bf09ae487ecbd53c0dac30aebaf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2019
ms.locfileid: "58262467"
---
# <a name="formatfromrawvalue-function"></a><span data-ttu-id="40d58-103">FormatFromRawValue 関数</span><span class="sxs-lookup"><span data-stu-id="40d58-103">FormatFromRawValue function</span></span>
<span data-ttu-id="40d58-104">1 つの生のパフォーマンス データ値が指定した形式に変換されます。この形式変換が時間ベースである場合は、2 つの生のパフォーマンス データ値が変換されます。</span><span class="sxs-lookup"><span data-stu-id="40d58-104">Converts one raw performance data value to the specified format, or two raw performance data values if the format conversion is time-based.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="40d58-105">構文</span><span class="sxs-lookup"><span data-stu-id="40d58-105">Syntax</span></span>

```
int FormatFromRawValue (
   [in] uint                    dwCounterType, 
   [in] uint                    dwFormat, 
   [in] long*                   pTimeBase,
   [in] PDH_RAW_COUNTER*        pRawValue1,
   [in] PDH_RAW_COUNTER*        pRawValue2,
   [out] PDH_FMT_COUNTERVALUE*  pFmtValue
); 
```

## <a name="parameters"></a><span data-ttu-id="40d58-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="40d58-106">Parameters</span></span>

`dwCounterType`\
<span data-ttu-id="40d58-107">[in]カウンターの型。</span><span class="sxs-lookup"><span data-stu-id="40d58-107">[in] The counter type.</span></span> <span data-ttu-id="40d58-108">カウンターの種類の一覧は、[WMI パフォーマンス カウンターの種類](/windows/desktop/WmiSdk/wmi-performance-counter-types)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40d58-108">For a list of counter types, see [WMI Performance Counter Types](/windows/desktop/WmiSdk/wmi-performance-counter-types).</span></span> <span data-ttu-id="40d58-109">`dwCounterType` 以外の任意のカウンター タイプ`PERF_LARGE_RAW_FRACTION`と`PERF_LARGE_RAW_BASE`します。</span><span class="sxs-lookup"><span data-stu-id="40d58-109">`dwCounterType` can be any counter type except for `PERF_LARGE_RAW_FRACTION` and `PERF_LARGE_RAW_BASE`.</span></span> 

`dwFormat`\
<span data-ttu-id="40d58-110">[in]生のパフォーマンス データを変換先の形式。</span><span class="sxs-lookup"><span data-stu-id="40d58-110">[in] The format to which to convert the raw performance data.</span></span> <span data-ttu-id="40d58-111">次の値のいずれかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="40d58-111">It can be one of the following values:</span></span>

|<span data-ttu-id="40d58-112">定数</span><span class="sxs-lookup"><span data-stu-id="40d58-112">Constant</span></span>  |<span data-ttu-id="40d58-113">値</span><span class="sxs-lookup"><span data-stu-id="40d58-113">Value</span></span>  |<span data-ttu-id="40d58-114">説明</span><span class="sxs-lookup"><span data-stu-id="40d58-114">Description</span></span> |
|---------|---------|---------|
| `PDH_FMT_DOUBLE` |<span data-ttu-id="40d58-115">0x00000200</span><span class="sxs-lookup"><span data-stu-id="40d58-115">0x00000200</span></span> | <span data-ttu-id="40d58-116">倍精度浮動小数点値として計算される値を返します。</span><span class="sxs-lookup"><span data-stu-id="40d58-116">Return the calculated value as a double-precision floating point value.</span></span> | 
| `PDH_FMT_LARGE` | <span data-ttu-id="40d58-117">0x00000400</span><span class="sxs-lookup"><span data-stu-id="40d58-117">0x00000400</span></span> | <span data-ttu-id="40d58-118">計算される値を 64 ビット整数として返します。</span><span class="sxs-lookup"><span data-stu-id="40d58-118">Return the calculated value as a 64-bit integer.</span></span> |
| `PDH_FMT_LONG` | <span data-ttu-id="40d58-119">0x00000100</span><span class="sxs-lookup"><span data-stu-id="40d58-119">0x00000100</span></span> | <span data-ttu-id="40d58-120">計算される値を 32 ビット整数として返します。</span><span class="sxs-lookup"><span data-stu-id="40d58-120">Return the calculated value as a 32-bit integer.</span></span> |

<span data-ttu-id="40d58-121">次のスケーリング フラグのいずれかの論理和前の値のいずれかのことができます。</span><span class="sxs-lookup"><span data-stu-id="40d58-121">One of the previous values can be ORed with one of the following scaling flags:</span></span>

|<span data-ttu-id="40d58-122">定数</span><span class="sxs-lookup"><span data-stu-id="40d58-122">Constant</span></span>  |<span data-ttu-id="40d58-123">値</span><span class="sxs-lookup"><span data-stu-id="40d58-123">Value</span></span>  |<span data-ttu-id="40d58-124">説明</span><span class="sxs-lookup"><span data-stu-id="40d58-124">Description</span></span> |
|---------|---------|---------|
| `PDH_FMT_NOSCALE` | <span data-ttu-id="40d58-125">0x00001000</span><span class="sxs-lookup"><span data-stu-id="40d58-125">0x00001000</span></span> | <span data-ttu-id="40d58-126">カウンターのスケール ファクターは適用されません。</span><span class="sxs-lookup"><span data-stu-id="40d58-126">Do not apply the counter's scaling factors.</span></span> |
| `PDH_FMT_1000` | <span data-ttu-id="40d58-127">0x00002000</span><span class="sxs-lookup"><span data-stu-id="40d58-127">0x00002000</span></span> | <span data-ttu-id="40d58-128">1000 で最終的な値を乗算します。</span><span class="sxs-lookup"><span data-stu-id="40d58-128">Multiply the final value by 1,000.</span></span> | 

`pTimeBase`\
<span data-ttu-id="40d58-129">[in]形式の変換に必要な場合、時間ベースへのポインター。</span><span class="sxs-lookup"><span data-stu-id="40d58-129">[in] A pointer to the time base, if necessary for the format conversion.</span></span> <span data-ttu-id="40d58-130">時間ベースの情報は、形式変換の必要はありません、このパラメーターの値は無視されます。</span><span class="sxs-lookup"><span data-stu-id="40d58-130">If time base information is not necessary for the format conversion, the value of this parameter is ignored.</span></span>

<span data-ttu-id="40d58-131">`pRawValue1`\ [in] へのポインターを[ `PDH_RAW_COUNTER` ](/windows/desktop/api/pdh/ns-pdh-_pdh_raw_counter)生のパフォーマンス値を表す構造体です。</span><span class="sxs-lookup"><span data-stu-id="40d58-131">`pRawValue1`\ [in] A pointer to a [`PDH_RAW_COUNTER`](/windows/desktop/api/pdh/ns-pdh-_pdh_raw_counter) structure that represents a raw performance value.</span></span>

`pRawValue2`\
<span data-ttu-id="40d58-132">[in]ポインターを[ `PDH_RAW_COUNTER` ](/windows/desktop/api/pdh/ns-pdh-_pdh_raw_counter) 2 番目の生のパフォーマンス値を表す構造体です。</span><span class="sxs-lookup"><span data-stu-id="40d58-132">[in] A pointer to a [`PDH_RAW_COUNTER`](/windows/desktop/api/pdh/ns-pdh-_pdh_raw_counter) structure that represents a second raw performance value.</span></span> <span data-ttu-id="40d58-133">2 番目の生のパフォーマンス値が必要でない場合、このパラメーターがあります`null`します。</span><span class="sxs-lookup"><span data-stu-id="40d58-133">If a second raw performance value is not necessary, this parameter should be `null`.</span></span>

`pFmtValue`\
<span data-ttu-id="40d58-134">[out]ポインターを[ `PDH_FMT_COUNTERVALUE` ](/windows/desktop/api/pdh/ns-pdh-_pdh_fmt_countervalue)を書式設定されたパフォーマンスの値を受け取る構造体。</span><span class="sxs-lookup"><span data-stu-id="40d58-134">[out] A pointer to a [`PDH_FMT_COUNTERVALUE`](/windows/desktop/api/pdh/ns-pdh-_pdh_fmt_countervalue) structure that receives the formatted performance value.</span></span>

## <a name="return-value"></a><span data-ttu-id="40d58-135">戻り値</span><span class="sxs-lookup"><span data-stu-id="40d58-135">Return value</span></span>

<span data-ttu-id="40d58-136">この関数では、次の値が返されます。</span><span class="sxs-lookup"><span data-stu-id="40d58-136">The following values are returned by this function:</span></span>

|<span data-ttu-id="40d58-137">定数</span><span class="sxs-lookup"><span data-stu-id="40d58-137">Constant</span></span>  |<span data-ttu-id="40d58-138">値</span><span class="sxs-lookup"><span data-stu-id="40d58-138">Value</span></span>  |<span data-ttu-id="40d58-139">説明</span><span class="sxs-lookup"><span data-stu-id="40d58-139">Description</span></span>  |
|---------|---------|---------|
| `ERROR_SUCCESS` | <span data-ttu-id="40d58-140">0</span><span class="sxs-lookup"><span data-stu-id="40d58-140">0</span></span> | <span data-ttu-id="40d58-141">関数呼び出しは成功します。</span><span class="sxs-lookup"><span data-stu-id="40d58-141">The function call is successful.</span></span> |
| `PDH_INVALID_ARGUMENT` | <span data-ttu-id="40d58-142">0xC0000BBD</span><span class="sxs-lookup"><span data-stu-id="40d58-142">0xC0000BBD</span></span> | <span data-ttu-id="40d58-143">必須の引数が不足しているか、正しくありません。</span><span class="sxs-lookup"><span data-stu-id="40d58-143">A required argument is missing or incorrect.</span></span> | 
| `PDH_INVALID_HANDLE` | <span data-ttu-id="40d58-144">0xC0000BBC</span><span class="sxs-lookup"><span data-stu-id="40d58-144">0xC0000BBC</span></span> | <span data-ttu-id="40d58-145">ハンドルが有効な PDH オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="40d58-145">The handle is not a valid PDH object.</span></span> |

## <a name="remarks"></a><span data-ttu-id="40d58-146">Remarks</span><span class="sxs-lookup"><span data-stu-id="40d58-146">Remarks</span></span>

<span data-ttu-id="40d58-147">この関数の呼び出しをラップする、 [FormatFromRawValue](https://docs.microsoft.com/previous-versions/ms231047(v=vs.85))関数。</span><span class="sxs-lookup"><span data-stu-id="40d58-147">This function wraps a call to the [FormatFromRawValue](https://docs.microsoft.com/previous-versions/ms231047(v=vs.85)) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="40d58-148">必要条件</span><span class="sxs-lookup"><span data-stu-id="40d58-148">Requirements</span></span>

 <span data-ttu-id="40d58-149">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="40d58-149">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="40d58-150">**ライブラリ:** どちら</span><span class="sxs-lookup"><span data-stu-id="40d58-150">**Library:** PerfCounter.dll</span></span>

 <span data-ttu-id="40d58-151">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="40d58-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="40d58-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="40d58-152">See also</span></span>

- [<span data-ttu-id="40d58-153">WMI およびパフォーマンス カウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="40d58-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
