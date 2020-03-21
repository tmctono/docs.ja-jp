---
title: 関数 (アンマネージ API リファレンス)
description: 関数は、生のパフォーマンス データを指定した形式に変換します。
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
ms.openlocfilehash: 0a7c0b8387f0c8e2b6e2ade94f7efeede75bd758
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176839"
---
# <a name="formatfromrawvalue-function"></a><span data-ttu-id="b5d8a-103">FormatFromRawValue 関数</span><span class="sxs-lookup"><span data-stu-id="b5d8a-103">FormatFromRawValue function</span></span>
<span data-ttu-id="b5d8a-104">1 つの生のパフォーマンス データ値が指定した形式に変換されます。この形式変換が時間ベースである場合は、2 つの生のパフォーマンス データ値が変換されます。</span><span class="sxs-lookup"><span data-stu-id="b5d8a-104">Converts one raw performance data value to the specified format, or two raw performance data values if the format conversion is time-based.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="b5d8a-105">構文</span><span class="sxs-lookup"><span data-stu-id="b5d8a-105">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="b5d8a-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b5d8a-106">Parameters</span></span>

`dwCounterType`\
<span data-ttu-id="b5d8a-107">[in]カウンターの種類。</span><span class="sxs-lookup"><span data-stu-id="b5d8a-107">[in] The counter type.</span></span> <span data-ttu-id="b5d8a-108">カウンターの種類の一覧については、「 [WMI パフォーマンス カウンターの種類](/windows/desktop/WmiSdk/wmi-performance-counter-types)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5d8a-108">For a list of counter types, see [WMI Performance Counter Types](/windows/desktop/WmiSdk/wmi-performance-counter-types).</span></span> <span data-ttu-id="b5d8a-109">`dwCounterType`は、 および 以外の`PERF_LARGE_RAW_FRACTION`任意`PERF_LARGE_RAW_BASE`のカウンター型にすることができます。</span><span class="sxs-lookup"><span data-stu-id="b5d8a-109">`dwCounterType` can be any counter type except for `PERF_LARGE_RAW_FRACTION` and `PERF_LARGE_RAW_BASE`.</span></span>

`dwFormat`\
<span data-ttu-id="b5d8a-110">[in]生のパフォーマンス データを変換する形式。</span><span class="sxs-lookup"><span data-stu-id="b5d8a-110">[in] The format to which to convert the raw performance data.</span></span> <span data-ttu-id="b5d8a-111">次のいずれかの値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="b5d8a-111">It can be one of the following values:</span></span>

|<span data-ttu-id="b5d8a-112">常時</span><span class="sxs-lookup"><span data-stu-id="b5d8a-112">Constant</span></span>  |<span data-ttu-id="b5d8a-113">Value</span><span class="sxs-lookup"><span data-stu-id="b5d8a-113">Value</span></span>  |<span data-ttu-id="b5d8a-114">説明</span><span class="sxs-lookup"><span data-stu-id="b5d8a-114">Description</span></span> |
|---------|---------|---------|
| `PDH_FMT_DOUBLE` |<span data-ttu-id="b5d8a-115">0x00000200</span><span class="sxs-lookup"><span data-stu-id="b5d8a-115">0x00000200</span></span> | <span data-ttu-id="b5d8a-116">計算された値を倍精度浮動小数点値として返します。</span><span class="sxs-lookup"><span data-stu-id="b5d8a-116">Return the calculated value as a double-precision floating point value.</span></span> |
| `PDH_FMT_LARGE` | <span data-ttu-id="b5d8a-117">0x00000400</span><span class="sxs-lookup"><span data-stu-id="b5d8a-117">0x00000400</span></span> | <span data-ttu-id="b5d8a-118">計算された値を 64 ビット整数で返します。</span><span class="sxs-lookup"><span data-stu-id="b5d8a-118">Return the calculated value as a 64-bit integer.</span></span> |
| `PDH_FMT_LONG` | <span data-ttu-id="b5d8a-119">0x00000100</span><span class="sxs-lookup"><span data-stu-id="b5d8a-119">0x00000100</span></span> | <span data-ttu-id="b5d8a-120">計算された値を 32 ビットの整数で返します。</span><span class="sxs-lookup"><span data-stu-id="b5d8a-120">Return the calculated value as a 32-bit integer.</span></span> |

<span data-ttu-id="b5d8a-121">上記の値の 1 つを、次のいずれかのスケーリング フラグを使用して、ORed にすることができます。</span><span class="sxs-lookup"><span data-stu-id="b5d8a-121">One of the previous values can be ORed with one of the following scaling flags:</span></span>

|<span data-ttu-id="b5d8a-122">常時</span><span class="sxs-lookup"><span data-stu-id="b5d8a-122">Constant</span></span>  |<span data-ttu-id="b5d8a-123">Value</span><span class="sxs-lookup"><span data-stu-id="b5d8a-123">Value</span></span>  |<span data-ttu-id="b5d8a-124">説明</span><span class="sxs-lookup"><span data-stu-id="b5d8a-124">Description</span></span> |
|---------|---------|---------|
| `PDH_FMT_NOSCALE` | <span data-ttu-id="b5d8a-125">0x00001000</span><span class="sxs-lookup"><span data-stu-id="b5d8a-125">0x00001000</span></span> | <span data-ttu-id="b5d8a-126">カウンタのスケーリング係数は適用しないでください。</span><span class="sxs-lookup"><span data-stu-id="b5d8a-126">Do not apply the counter's scaling factors.</span></span> |
| `PDH_FMT_1000` | <span data-ttu-id="b5d8a-127">0x00002000</span><span class="sxs-lookup"><span data-stu-id="b5d8a-127">0x00002000</span></span> | <span data-ttu-id="b5d8a-128">最終的な値に 1,000 を掛けます。</span><span class="sxs-lookup"><span data-stu-id="b5d8a-128">Multiply the final value by 1,000.</span></span> |

`pTimeBase`\
<span data-ttu-id="b5d8a-129">[in]フォーマット変換に必要な場合は、時間ベースへのポインタ。</span><span class="sxs-lookup"><span data-stu-id="b5d8a-129">[in] A pointer to the time base, if necessary for the format conversion.</span></span> <span data-ttu-id="b5d8a-130">フォーマット変換に時間ベース情報が必要ない場合、このパラメーターの値は無視されます。</span><span class="sxs-lookup"><span data-stu-id="b5d8a-130">If time base information is not necessary for the format conversion, the value of this parameter is ignored.</span></span>

`pRawValue1`\
<span data-ttu-id="b5d8a-131">[in]生のパフォーマンス値[`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter)を表す構造体へのポインター。</span><span class="sxs-lookup"><span data-stu-id="b5d8a-131">[in] A pointer to a [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) structure that represents a raw performance value.</span></span>

`pRawValue2`\
<span data-ttu-id="b5d8a-132">[in]2 番目の[`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter)生のパフォーマンス値を表す構造体へのポインター。</span><span class="sxs-lookup"><span data-stu-id="b5d8a-132">[in] A pointer to a [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) structure that represents a second raw performance value.</span></span> <span data-ttu-id="b5d8a-133">2 番目の生のパフォーマンス値が必要ない場合、この`null`パラメーターは にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5d8a-133">If a second raw performance value is not necessary, this parameter should be `null`.</span></span>

`pFmtValue`\
<span data-ttu-id="b5d8a-134">[アウト]フォーマットされたパフォーマンス値[`PDH_FMT_COUNTERVALUE`](/windows/win32/api/pdh/ns-pdh-pdh_fmt_countervalue)を受け取る構造体へのポインター。</span><span class="sxs-lookup"><span data-stu-id="b5d8a-134">[out] A pointer to a [`PDH_FMT_COUNTERVALUE`](/windows/win32/api/pdh/ns-pdh-pdh_fmt_countervalue) structure that receives the formatted performance value.</span></span>

## <a name="return-value"></a><span data-ttu-id="b5d8a-135">戻り値</span><span class="sxs-lookup"><span data-stu-id="b5d8a-135">Return value</span></span>

<span data-ttu-id="b5d8a-136">この関数では、次の値が返されます。</span><span class="sxs-lookup"><span data-stu-id="b5d8a-136">The following values are returned by this function:</span></span>

|<span data-ttu-id="b5d8a-137">常時</span><span class="sxs-lookup"><span data-stu-id="b5d8a-137">Constant</span></span>  |<span data-ttu-id="b5d8a-138">Value</span><span class="sxs-lookup"><span data-stu-id="b5d8a-138">Value</span></span>  |<span data-ttu-id="b5d8a-139">説明</span><span class="sxs-lookup"><span data-stu-id="b5d8a-139">Description</span></span>  |
|---------|---------|---------|
| `ERROR_SUCCESS` | <span data-ttu-id="b5d8a-140">0</span><span class="sxs-lookup"><span data-stu-id="b5d8a-140">0</span></span> | <span data-ttu-id="b5d8a-141">関数呼び出しが成功しました。</span><span class="sxs-lookup"><span data-stu-id="b5d8a-141">The function call is successful.</span></span> |
| `PDH_INVALID_ARGUMENT` | <span data-ttu-id="b5d8a-142">0xC0000BBD</span><span class="sxs-lookup"><span data-stu-id="b5d8a-142">0xC0000BBD</span></span> | <span data-ttu-id="b5d8a-143">必要な引数がないか、または正しくありません。</span><span class="sxs-lookup"><span data-stu-id="b5d8a-143">A required argument is missing or incorrect.</span></span> |
| `PDH_INVALID_HANDLE` | <span data-ttu-id="b5d8a-144">0xC0000BBC</span><span class="sxs-lookup"><span data-stu-id="b5d8a-144">0xC0000BBC</span></span> | <span data-ttu-id="b5d8a-145">ハンドルが有効な PDH オブジェクトではありません。</span><span class="sxs-lookup"><span data-stu-id="b5d8a-145">The handle is not a valid PDH object.</span></span> |

## <a name="remarks"></a><span data-ttu-id="b5d8a-146">解説</span><span class="sxs-lookup"><span data-stu-id="b5d8a-146">Remarks</span></span>

<span data-ttu-id="b5d8a-147">この関数は[、関数の](https://docs.microsoft.com/previous-versions/ms231047(v=vs.85))呼び出しをラップします。</span><span class="sxs-lookup"><span data-stu-id="b5d8a-147">This function wraps a call to the [FormatFromRawValue](https://docs.microsoft.com/previous-versions/ms231047(v=vs.85)) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="b5d8a-148">必要条件</span><span class="sxs-lookup"><span data-stu-id="b5d8a-148">Requirements</span></span>

 <span data-ttu-id="b5d8a-149">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5d8a-149">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="b5d8a-150">**ライブラリ:** パーフカウンター.dll</span><span class="sxs-lookup"><span data-stu-id="b5d8a-150">**Library:** PerfCounter.dll</span></span>

 <span data-ttu-id="b5d8a-151">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b5d8a-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="b5d8a-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="b5d8a-152">See also</span></span>

- [<span data-ttu-id="b5d8a-153">WMI およびパフォーマンス カウンター (アンマネージド API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="b5d8a-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
