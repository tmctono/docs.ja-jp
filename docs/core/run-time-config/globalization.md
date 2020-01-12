---
title: グローバリゼーションの構成設定
description: .NET Core アプリのグローバリゼーションの側面 (たとえば、日本語の日付の解析方法など) を構成するランタイム設定について説明します。
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 76cd4a0a0f93f4df3ff243c6024b952576e8e6cb
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740546"
---
# <a name="run-time-configuration-options-for-globalization"></a><span data-ttu-id="5a69f-103">グローバリゼーションのランタイム構成オプション</span><span class="sxs-lookup"><span data-stu-id="5a69f-103">Run-time configuration options for globalization</span></span>

## <a name="invariant-mode"></a><span data-ttu-id="5a69f-104">インバリアント モード</span><span class="sxs-lookup"><span data-stu-id="5a69f-104">Invariant mode</span></span>

- <span data-ttu-id="5a69f-105">.NET Core を、カルチャ固有のデータや動作にアクセスせずにグローバリゼーション インバリアント モードで実行するか、またはカルチャ データにアクセスできるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="5a69f-105">Determines whether a .NET Core app runs in globalization invariant mode without access to culture-specific data and behavior or whether it has access to cultural data.</span></span>
- <span data-ttu-id="5a69f-106">既定:カルチャ データにアクセスしてアプリを実行します (`false`)。</span><span class="sxs-lookup"><span data-stu-id="5a69f-106">Default: Run the app with access to cultural data (`false`).</span></span>
- <span data-ttu-id="5a69f-107">詳細については、「[.NET Core のグローバリゼーション インバリアント モード](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a69f-107">For more information, see [.NET Core globalization invariant mode](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).</span></span>

| | <span data-ttu-id="5a69f-108">設定の名前</span><span class="sxs-lookup"><span data-stu-id="5a69f-108">Setting name</span></span> | <span data-ttu-id="5a69f-109">値</span><span class="sxs-lookup"><span data-stu-id="5a69f-109">Values</span></span> |
| - | - | - |
| <span data-ttu-id="5a69f-110">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="5a69f-110">**runtimeconfig.json**</span></span> | `System.Globalization.Invariant` | <span data-ttu-id="5a69f-111">`false` - カルチャ データにアクセスする</span><span class="sxs-lookup"><span data-stu-id="5a69f-111">`false` - access to cultural data</span></span><br/><span data-ttu-id="5a69f-112">`true` - インバリアント モードで実行する</span><span class="sxs-lookup"><span data-stu-id="5a69f-112">`true` - run in invariant mode</span></span> |
| <span data-ttu-id="5a69f-113">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="5a69f-113">**Environment variable**</span></span> | `DOTNET_SYSTEM_GLOBALIZATION_INVARIANT` | <span data-ttu-id="5a69f-114">`0` - カルチャ データにアクセスする</span><span class="sxs-lookup"><span data-stu-id="5a69f-114">`0` - access to cultural data</span></span><br/><span data-ttu-id="5a69f-115">`1` - インバリアント モードで実行する</span><span class="sxs-lookup"><span data-stu-id="5a69f-115">`1` - run in invariant mode</span></span> |

## <a name="era-year-ranges"></a><span data-ttu-id="5a69f-116">年号の範囲</span><span class="sxs-lookup"><span data-stu-id="5a69f-116">Era year ranges</span></span>

- <span data-ttu-id="5a69f-117">複数の年号をサポートするカレンダーの範囲チェックを緩和するか、または日付が年号の日付範囲をオーバーフローした場合に <xref:System.ArgumentOutOfRangeException> をスローするかを決定します。</span><span class="sxs-lookup"><span data-stu-id="5a69f-117">Determines whether range checks for calendars that support multiple eras are relaxed or whether dates that overflow an era's date range throw an <xref:System.ArgumentOutOfRangeException>.</span></span>
- <span data-ttu-id="5a69f-118">既定:範囲チェックを緩和します (`false`)。</span><span class="sxs-lookup"><span data-stu-id="5a69f-118">Default: Range checks are relaxed (`false`).</span></span>
- <span data-ttu-id="5a69f-119">詳細については、「[カレンダー、時代 (年号)、および日付範囲: 緩やかな範囲のチェック](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a69f-119">For more information, see [Calendars, eras, and date ranges: Relaxed range checks](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks).</span></span>

| | <span data-ttu-id="5a69f-120">設定の名前</span><span class="sxs-lookup"><span data-stu-id="5a69f-120">Setting name</span></span> | <span data-ttu-id="5a69f-121">値</span><span class="sxs-lookup"><span data-stu-id="5a69f-121">Values</span></span> |
| - | - | - |
| <span data-ttu-id="5a69f-122">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="5a69f-122">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.EnforceJapaneseEraYearRanges` | <span data-ttu-id="5a69f-123">`false` - 緩和された範囲チェック</span><span class="sxs-lookup"><span data-stu-id="5a69f-123">`false` - relaxed range checks</span></span><br/><span data-ttu-id="5a69f-124">`true` - オーバーフローによって例外が発生する</span><span class="sxs-lookup"><span data-stu-id="5a69f-124">`true` - overflows cause an exception</span></span> |
| <span data-ttu-id="5a69f-125">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="5a69f-125">**Environment variable**</span></span> | <span data-ttu-id="5a69f-126">N/A</span><span class="sxs-lookup"><span data-stu-id="5a69f-126">N/A</span></span> | <span data-ttu-id="5a69f-127">N/A</span><span class="sxs-lookup"><span data-stu-id="5a69f-127">N/A</span></span> |

## <a name="japanese-date-parsing"></a><span data-ttu-id="5a69f-128">日本の日付の解析</span><span class="sxs-lookup"><span data-stu-id="5a69f-128">Japanese date parsing</span></span>

- <span data-ttu-id="5a69f-129">年として "1" または "元年" のいずれかを含む文字列を正しく解析するか、または "1" のみをサポートするかを決定します。</span><span class="sxs-lookup"><span data-stu-id="5a69f-129">Determines whether a string that contains either "1" or "Gannen" as the year parses successfully or whether only "1" is supported.</span></span>
- <span data-ttu-id="5a69f-130">既定:"1" または "元年" のいずれかを含む文字列を年として解析します (`false`)。</span><span class="sxs-lookup"><span data-stu-id="5a69f-130">Default: Parse strings that contain either "1" or "Gannen" as the year (`false`).</span></span>
- <span data-ttu-id="5a69f-131">詳細については、「[複数の時代 (年号) のカレンダーで日付を表す](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a69f-131">For more information, see [Represent dates in calendars with multiple eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span></span>

| | <span data-ttu-id="5a69f-132">設定の名前</span><span class="sxs-lookup"><span data-stu-id="5a69f-132">Setting name</span></span> | <span data-ttu-id="5a69f-133">値</span><span class="sxs-lookup"><span data-stu-id="5a69f-133">Values</span></span> |
| - | - | - |
| <span data-ttu-id="5a69f-134">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="5a69f-134">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.EnforceLegacyJapaneseDateParsing` | <span data-ttu-id="5a69f-135">`false` - "元年" または "1" をサポートする</span><span class="sxs-lookup"><span data-stu-id="5a69f-135">`false` - "Gannen" or "1" is supported</span></span><br/><span data-ttu-id="5a69f-136">`true` - "1" のみをサポートする</span><span class="sxs-lookup"><span data-stu-id="5a69f-136">`true` - only "1" is supported</span></span> |
| <span data-ttu-id="5a69f-137">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="5a69f-137">**Environment variable**</span></span> | <span data-ttu-id="5a69f-138">N/A</span><span class="sxs-lookup"><span data-stu-id="5a69f-138">N/A</span></span> | <span data-ttu-id="5a69f-139">N/A</span><span class="sxs-lookup"><span data-stu-id="5a69f-139">N/A</span></span> |

## <a name="japanese-year-format"></a><span data-ttu-id="5a69f-140">日本の年の形式</span><span class="sxs-lookup"><span data-stu-id="5a69f-140">Japanese year format</span></span>

- <span data-ttu-id="5a69f-141">和暦の元年を "元年" または "1" のどちらで書式設定するかを決定します。</span><span class="sxs-lookup"><span data-stu-id="5a69f-141">Determines whether the first year of a Japanese calendar era is formatted as "Gannen" or as a number.</span></span>
- <span data-ttu-id="5a69f-142">既定:元年を "元年" として書式設定します (`false`)。</span><span class="sxs-lookup"><span data-stu-id="5a69f-142">Default: Format the first year as "Gannen" (`false`).</span></span>
- <span data-ttu-id="5a69f-143">詳細については、「[複数の時代 (年号) のカレンダーで日付を表す](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a69f-143">For more information, see [Represent dates in calendars with multiple eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span></span>

| | <span data-ttu-id="5a69f-144">設定の名前</span><span class="sxs-lookup"><span data-stu-id="5a69f-144">Setting name</span></span> | <span data-ttu-id="5a69f-145">値</span><span class="sxs-lookup"><span data-stu-id="5a69f-145">Values</span></span> |
| - | - | - |
| <span data-ttu-id="5a69f-146">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="5a69f-146">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.FormatJapaneseFirstYearAsANumber` | <span data-ttu-id="5a69f-147">`false` - "元年" として書式設定する</span><span class="sxs-lookup"><span data-stu-id="5a69f-147">`false` - format as "Gannen"</span></span><br/><span data-ttu-id="5a69f-148">`true` - 数字として書式設定する</span><span class="sxs-lookup"><span data-stu-id="5a69f-148">`true` - format as number</span></span> |
| <span data-ttu-id="5a69f-149">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="5a69f-149">**Environment variable**</span></span> | <span data-ttu-id="5a69f-150">N/A</span><span class="sxs-lookup"><span data-stu-id="5a69f-150">N/A</span></span> | <span data-ttu-id="5a69f-151">N/A</span><span class="sxs-lookup"><span data-stu-id="5a69f-151">N/A</span></span> |
