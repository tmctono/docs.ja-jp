---
title: FormatFromRawValue 関数 (アンマネージ API リファレンス)
description: FormatFromRawValue 関数は、生のパフォーマンスデータを指定された形式に変換します。
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
ms.openlocfilehash: 681d7ce42b2b8d16353e4f5b3523f1a953a49d95
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "69037895"
---
# <a name="formatfromrawvalue-function"></a><span data-ttu-id="84a24-103">FormatFromRawValue 関数</span><span class="sxs-lookup"><span data-stu-id="84a24-103">FormatFromRawValue function</span></span>
<span data-ttu-id="84a24-104">1 つの生のパフォーマンス データ値が指定した形式に変換されます。この形式変換が時間ベースである場合は、2 つの生のパフォーマンス データ値が変換されます。</span><span class="sxs-lookup"><span data-stu-id="84a24-104">Converts one raw performance data value to the specified format, or two raw performance data values if the format conversion is time-based.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="84a24-105">構文</span><span class="sxs-lookup"><span data-stu-id="84a24-105">Syntax</span></span>

```cpp
int FormatFromRawValue (
   [in] uint                    dwCounterType, 
   [in] uint                    dwFormat, 
   [in] long*                   pTimeBase,
   [in] PDH_RAW_COUNTER*        pRawValue1,
   [in] PDH_RAW_COUNTER*        pRawValue2,
   [out] PDH_FMT_COUNTERVALUE*  pFmtValue
); 
```

## <a name="parameters"></a><span data-ttu-id="84a24-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="84a24-106">Parameters</span></span>

`dwCounterType`\
<span data-ttu-id="84a24-107">からカウンターの種類。</span><span class="sxs-lookup"><span data-stu-id="84a24-107">[in] The counter type.</span></span> <span data-ttu-id="84a24-108">カウンターの種類の一覧については、「 [WMI パフォーマンスカウンターの種類](/windows/desktop/WmiSdk/wmi-performance-counter-types)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84a24-108">For a list of counter types, see [WMI Performance Counter Types](/windows/desktop/WmiSdk/wmi-performance-counter-types).</span></span> <span data-ttu-id="84a24-109">`dwCounterType`には、および`PERF_LARGE_RAW_FRACTION` `PERF_LARGE_RAW_BASE`を除く任意の種類のカウンターを指定できます。</span><span class="sxs-lookup"><span data-stu-id="84a24-109">`dwCounterType` can be any counter type except for `PERF_LARGE_RAW_FRACTION` and `PERF_LARGE_RAW_BASE`.</span></span> 

`dwFormat`\
<span data-ttu-id="84a24-110">から生のパフォーマンスデータを変換する形式。</span><span class="sxs-lookup"><span data-stu-id="84a24-110">[in] The format to which to convert the raw performance data.</span></span> <span data-ttu-id="84a24-111">次のいずれかの値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="84a24-111">It can be one of the following values:</span></span>

|<span data-ttu-id="84a24-112">定数</span><span class="sxs-lookup"><span data-stu-id="84a24-112">Constant</span></span>  |<span data-ttu-id="84a24-113">Value</span><span class="sxs-lookup"><span data-stu-id="84a24-113">Value</span></span>  |<span data-ttu-id="84a24-114">説明</span><span class="sxs-lookup"><span data-stu-id="84a24-114">Description</span></span> |
|---------|---------|---------|
| `PDH_FMT_DOUBLE` |<span data-ttu-id="84a24-115">0x00000200</span><span class="sxs-lookup"><span data-stu-id="84a24-115">0x00000200</span></span> | <span data-ttu-id="84a24-116">計算された値を倍精度浮動小数点値として返します。</span><span class="sxs-lookup"><span data-stu-id="84a24-116">Return the calculated value as a double-precision floating point value.</span></span> | 
| `PDH_FMT_LARGE` | <span data-ttu-id="84a24-117">0x00000400</span><span class="sxs-lookup"><span data-stu-id="84a24-117">0x00000400</span></span> | <span data-ttu-id="84a24-118">計算された値を64ビット整数として返します。</span><span class="sxs-lookup"><span data-stu-id="84a24-118">Return the calculated value as a 64-bit integer.</span></span> |
| `PDH_FMT_LONG` | <span data-ttu-id="84a24-119">0x00000100</span><span class="sxs-lookup"><span data-stu-id="84a24-119">0x00000100</span></span> | <span data-ttu-id="84a24-120">計算された値を32ビット整数として返します。</span><span class="sxs-lookup"><span data-stu-id="84a24-120">Return the calculated value as a 32-bit integer.</span></span> |

<span data-ttu-id="84a24-121">前の値の1つは、次のいずれかのスケーリングフラグと共に使用できます。</span><span class="sxs-lookup"><span data-stu-id="84a24-121">One of the previous values can be ORed with one of the following scaling flags:</span></span>

|<span data-ttu-id="84a24-122">定数</span><span class="sxs-lookup"><span data-stu-id="84a24-122">Constant</span></span>  |<span data-ttu-id="84a24-123">Value</span><span class="sxs-lookup"><span data-stu-id="84a24-123">Value</span></span>  |<span data-ttu-id="84a24-124">説明</span><span class="sxs-lookup"><span data-stu-id="84a24-124">Description</span></span> |
|---------|---------|---------|
| `PDH_FMT_NOSCALE` | <span data-ttu-id="84a24-125">0x00001000</span><span class="sxs-lookup"><span data-stu-id="84a24-125">0x00001000</span></span> | <span data-ttu-id="84a24-126">カウンターのスケールファクターは適用しないでください。</span><span class="sxs-lookup"><span data-stu-id="84a24-126">Do not apply the counter's scaling factors.</span></span> |
| `PDH_FMT_1000` | <span data-ttu-id="84a24-127">0x00002000</span><span class="sxs-lookup"><span data-stu-id="84a24-127">0x00002000</span></span> | <span data-ttu-id="84a24-128">最終的な値を1000で乗算します。</span><span class="sxs-lookup"><span data-stu-id="84a24-128">Multiply the final value by 1,000.</span></span> | 

`pTimeBase`\
<span data-ttu-id="84a24-129">から形式変換に必要な場合は、タイムベースへのポインター。</span><span class="sxs-lookup"><span data-stu-id="84a24-129">[in] A pointer to the time base, if necessary for the format conversion.</span></span> <span data-ttu-id="84a24-130">形式変換に時間ベース情報が不要な場合、このパラメーターの値は無視されます。</span><span class="sxs-lookup"><span data-stu-id="84a24-130">If time base information is not necessary for the format conversion, the value of this parameter is ignored.</span></span>

<span data-ttu-id="84a24-131">`pRawValue1`\ [in] 生のパフォーマンス値[`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter)を表す構造体へのポインター。</span><span class="sxs-lookup"><span data-stu-id="84a24-131">`pRawValue1`\ [in] A pointer to a [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) structure that represents a raw performance value.</span></span>

`pRawValue2`\
<span data-ttu-id="84a24-132">から2番目の[`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter)生のパフォーマンス値を表す構造体へのポインター。</span><span class="sxs-lookup"><span data-stu-id="84a24-132">[in] A pointer to a [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) structure that represents a second raw performance value.</span></span> <span data-ttu-id="84a24-133">2番目の生のパフォーマンス値が不要な場合、この`null`パラメーターはにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="84a24-133">If a second raw performance value is not necessary, this parameter should be `null`.</span></span>

`pFmtValue`\
<span data-ttu-id="84a24-134">入出力書式設定され[`PDH_FMT_COUNTERVALUE`](/windows/win32/api/pdh/ns-pdh-pdh_fmt_countervalue)たパフォーマンス値を受け取る構造体へのポインター。</span><span class="sxs-lookup"><span data-stu-id="84a24-134">[out] A pointer to a [`PDH_FMT_COUNTERVALUE`](/windows/win32/api/pdh/ns-pdh-pdh_fmt_countervalue) structure that receives the formatted performance value.</span></span>

## <a name="return-value"></a><span data-ttu-id="84a24-135">戻り値</span><span class="sxs-lookup"><span data-stu-id="84a24-135">Return value</span></span>

<span data-ttu-id="84a24-136">この関数によって返される値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="84a24-136">The following values are returned by this function:</span></span>

|<span data-ttu-id="84a24-137">定数</span><span class="sxs-lookup"><span data-stu-id="84a24-137">Constant</span></span>  |<span data-ttu-id="84a24-138">Value</span><span class="sxs-lookup"><span data-stu-id="84a24-138">Value</span></span>  |<span data-ttu-id="84a24-139">説明</span><span class="sxs-lookup"><span data-stu-id="84a24-139">Description</span></span>  |
|---------|---------|---------|
| `ERROR_SUCCESS` | <span data-ttu-id="84a24-140">0</span><span class="sxs-lookup"><span data-stu-id="84a24-140">0</span></span> | <span data-ttu-id="84a24-141">関数の呼び出しは成功しました。</span><span class="sxs-lookup"><span data-stu-id="84a24-141">The function call is successful.</span></span> |
| `PDH_INVALID_ARGUMENT` | <span data-ttu-id="84a24-142">0xC0000BBD</span><span class="sxs-lookup"><span data-stu-id="84a24-142">0xC0000BBD</span></span> | <span data-ttu-id="84a24-143">必須の引数が指定されていないか、正しくありません。</span><span class="sxs-lookup"><span data-stu-id="84a24-143">A required argument is missing or incorrect.</span></span> | 
| `PDH_INVALID_HANDLE` | <span data-ttu-id="84a24-144">0xC0000BBC</span><span class="sxs-lookup"><span data-stu-id="84a24-144">0xC0000BBC</span></span> | <span data-ttu-id="84a24-145">ハンドルは、有効な PDH オブジェクトではありません。</span><span class="sxs-lookup"><span data-stu-id="84a24-145">The handle is not a valid PDH object.</span></span> |

## <a name="remarks"></a><span data-ttu-id="84a24-146">Remarks</span><span class="sxs-lookup"><span data-stu-id="84a24-146">Remarks</span></span>

<span data-ttu-id="84a24-147">この関数は、 [FormatFromRawValue](https://docs.microsoft.com/previous-versions/ms231047(v=vs.85))関数の呼び出しをラップします。</span><span class="sxs-lookup"><span data-stu-id="84a24-147">This function wraps a call to the [FormatFromRawValue](https://docs.microsoft.com/previous-versions/ms231047(v=vs.85)) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="84a24-148">必要条件</span><span class="sxs-lookup"><span data-stu-id="84a24-148">Requirements</span></span>

 <span data-ttu-id="84a24-149">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="84a24-149">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="84a24-150">**ライブラリ**PerfCounter .dll</span><span class="sxs-lookup"><span data-stu-id="84a24-150">**Library:** PerfCounter.dll</span></span>

 <span data-ttu-id="84a24-151">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="84a24-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="84a24-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="84a24-152">See also</span></span>

- [<span data-ttu-id="84a24-153">WMI およびパフォーマンスカウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="84a24-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
