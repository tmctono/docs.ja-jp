---
title: グローバリゼーションの構成設定
description: .NET Core アプリのグローバリゼーションの側面 (たとえば、日本語の日付の解析方法など) を構成するランタイム設定について説明します。
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 3764d0eb714c094b44ae843a1e626073ff8d82e4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "76733457"
---
# <a name="run-time-configuration-options-for-globalization"></a><span data-ttu-id="bcfb1-103">グローバリゼーションのランタイム構成オプション</span><span class="sxs-lookup"><span data-stu-id="bcfb1-103">Run-time configuration options for globalization</span></span>

## <a name="invariant-mode"></a><span data-ttu-id="bcfb1-104">インバリアント モード</span><span class="sxs-lookup"><span data-stu-id="bcfb1-104">Invariant mode</span></span>

- <span data-ttu-id="bcfb1-105">.NET Core を、カルチャ固有のデータや動作にアクセスせずにグローバリゼーション インバリアント モードで実行するか、またはカルチャ データにアクセスできるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="bcfb1-105">Determines whether a .NET Core app runs in globalization invariant mode without access to culture-specific data and behavior or whether it has access to cultural data.</span></span>
- <span data-ttu-id="bcfb1-106">既定:カルチャ データにアクセスしてアプリを実行します (`false`)。</span><span class="sxs-lookup"><span data-stu-id="bcfb1-106">Default: Run the app with access to cultural data (`false`).</span></span>
- <span data-ttu-id="bcfb1-107">詳細については、「[.NET Core のグローバリゼーション インバリアント モード](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bcfb1-107">For more information, see [.NET Core globalization invariant mode](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).</span></span>

| | <span data-ttu-id="bcfb1-108">設定の名前</span><span class="sxs-lookup"><span data-stu-id="bcfb1-108">Setting name</span></span> | <span data-ttu-id="bcfb1-109">値</span><span class="sxs-lookup"><span data-stu-id="bcfb1-109">Values</span></span> |
| - | - | - |
| <span data-ttu-id="bcfb1-110">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="bcfb1-110">**runtimeconfig.json**</span></span> | `System.Globalization.Invariant` | <span data-ttu-id="bcfb1-111">`false` - カルチャ データにアクセスする</span><span class="sxs-lookup"><span data-stu-id="bcfb1-111">`false` - access to cultural data</span></span><br/><span data-ttu-id="bcfb1-112">`true` - インバリアント モードで実行する</span><span class="sxs-lookup"><span data-stu-id="bcfb1-112">`true` - run in invariant mode</span></span> |
| <span data-ttu-id="bcfb1-113">**MSBuild のプロパティ**</span><span class="sxs-lookup"><span data-stu-id="bcfb1-113">**MSBuild property**</span></span> | `InvariantGlobalization` | <span data-ttu-id="bcfb1-114">`false` - カルチャ データにアクセスする</span><span class="sxs-lookup"><span data-stu-id="bcfb1-114">`false` - access to cultural data</span></span><br/><span data-ttu-id="bcfb1-115">`true` - インバリアント モードで実行する</span><span class="sxs-lookup"><span data-stu-id="bcfb1-115">`true` - run in invariant mode</span></span> |
| <span data-ttu-id="bcfb1-116">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="bcfb1-116">**Environment variable**</span></span> | `DOTNET_SYSTEM_GLOBALIZATION_INVARIANT` | <span data-ttu-id="bcfb1-117">`0` - カルチャ データにアクセスする</span><span class="sxs-lookup"><span data-stu-id="bcfb1-117">`0` - access to cultural data</span></span><br/><span data-ttu-id="bcfb1-118">`1` - インバリアント モードで実行する</span><span class="sxs-lookup"><span data-stu-id="bcfb1-118">`1` - run in invariant mode</span></span> |

### <a name="examples"></a><span data-ttu-id="bcfb1-119">使用例</span><span class="sxs-lookup"><span data-stu-id="bcfb1-119">Examples</span></span>

<span data-ttu-id="bcfb1-120">*runtimeconfig.json* ファイル:</span><span class="sxs-lookup"><span data-stu-id="bcfb1-120">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Globalization.Invariant": true
      }
   }
}
```

<span data-ttu-id="bcfb1-121">プロジェクト ファイル:</span><span class="sxs-lookup"><span data-stu-id="bcfb1-121">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <InvariantGlobalization>true</InvariantGlobalization>
  </PropertyGroup>

</Project>
```

## <a name="era-year-ranges"></a><span data-ttu-id="bcfb1-122">年号の範囲</span><span class="sxs-lookup"><span data-stu-id="bcfb1-122">Era year ranges</span></span>

- <span data-ttu-id="bcfb1-123">複数の年号をサポートするカレンダーの範囲チェックを緩和するか、または日付が年号の日付範囲をオーバーフローした場合に <xref:System.ArgumentOutOfRangeException> をスローするかを決定します。</span><span class="sxs-lookup"><span data-stu-id="bcfb1-123">Determines whether range checks for calendars that support multiple eras are relaxed or whether dates that overflow an era's date range throw an <xref:System.ArgumentOutOfRangeException>.</span></span>
- <span data-ttu-id="bcfb1-124">既定:範囲チェックを緩和します (`false`)。</span><span class="sxs-lookup"><span data-stu-id="bcfb1-124">Default: Range checks are relaxed (`false`).</span></span>
- <span data-ttu-id="bcfb1-125">詳細については、「[カレンダー、時代 (年号)、および日付範囲: 緩やかな範囲のチェック](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bcfb1-125">For more information, see [Calendars, eras, and date ranges: Relaxed range checks](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks).</span></span>

| | <span data-ttu-id="bcfb1-126">設定の名前</span><span class="sxs-lookup"><span data-stu-id="bcfb1-126">Setting name</span></span> | <span data-ttu-id="bcfb1-127">値</span><span class="sxs-lookup"><span data-stu-id="bcfb1-127">Values</span></span> |
| - | - | - |
| <span data-ttu-id="bcfb1-128">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="bcfb1-128">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.EnforceJapaneseEraYearRanges` | <span data-ttu-id="bcfb1-129">`false` - 緩和された範囲チェック</span><span class="sxs-lookup"><span data-stu-id="bcfb1-129">`false` - relaxed range checks</span></span><br/><span data-ttu-id="bcfb1-130">`true` - オーバーフローによって例外が発生する</span><span class="sxs-lookup"><span data-stu-id="bcfb1-130">`true` - overflows cause an exception</span></span> |
| <span data-ttu-id="bcfb1-131">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="bcfb1-131">**Environment variable**</span></span> | <span data-ttu-id="bcfb1-132">N/A</span><span class="sxs-lookup"><span data-stu-id="bcfb1-132">N/A</span></span> | <span data-ttu-id="bcfb1-133">N/A</span><span class="sxs-lookup"><span data-stu-id="bcfb1-133">N/A</span></span> |

## <a name="japanese-date-parsing"></a><span data-ttu-id="bcfb1-134">日本の日付の解析</span><span class="sxs-lookup"><span data-stu-id="bcfb1-134">Japanese date parsing</span></span>

- <span data-ttu-id="bcfb1-135">年として "1" または "元年" のいずれかを含む文字列を正しく解析するか、または "1" のみをサポートするかを決定します。</span><span class="sxs-lookup"><span data-stu-id="bcfb1-135">Determines whether a string that contains either "1" or "Gannen" as the year parses successfully or whether only "1" is supported.</span></span>
- <span data-ttu-id="bcfb1-136">既定:"1" または "元年" のいずれかを含む文字列を年として解析します (`false`)。</span><span class="sxs-lookup"><span data-stu-id="bcfb1-136">Default: Parse strings that contain either "1" or "Gannen" as the year (`false`).</span></span>
- <span data-ttu-id="bcfb1-137">詳細については、「[複数の時代 (年号) のカレンダーで日付を表す](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bcfb1-137">For more information, see [Represent dates in calendars with multiple eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span></span>

| | <span data-ttu-id="bcfb1-138">設定の名前</span><span class="sxs-lookup"><span data-stu-id="bcfb1-138">Setting name</span></span> | <span data-ttu-id="bcfb1-139">値</span><span class="sxs-lookup"><span data-stu-id="bcfb1-139">Values</span></span> |
| - | - | - |
| <span data-ttu-id="bcfb1-140">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="bcfb1-140">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.EnforceLegacyJapaneseDateParsing` | <span data-ttu-id="bcfb1-141">`false` - "元年" または "1" をサポートする</span><span class="sxs-lookup"><span data-stu-id="bcfb1-141">`false` - "Gannen" or "1" is supported</span></span><br/><span data-ttu-id="bcfb1-142">`true` - "1" のみをサポートする</span><span class="sxs-lookup"><span data-stu-id="bcfb1-142">`true` - only "1" is supported</span></span> |
| <span data-ttu-id="bcfb1-143">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="bcfb1-143">**Environment variable**</span></span> | <span data-ttu-id="bcfb1-144">N/A</span><span class="sxs-lookup"><span data-stu-id="bcfb1-144">N/A</span></span> | <span data-ttu-id="bcfb1-145">N/A</span><span class="sxs-lookup"><span data-stu-id="bcfb1-145">N/A</span></span> |

## <a name="japanese-year-format"></a><span data-ttu-id="bcfb1-146">日本の年の形式</span><span class="sxs-lookup"><span data-stu-id="bcfb1-146">Japanese year format</span></span>

- <span data-ttu-id="bcfb1-147">和暦の元年を "元年" または "1" のどちらで書式設定するかを決定します。</span><span class="sxs-lookup"><span data-stu-id="bcfb1-147">Determines whether the first year of a Japanese calendar era is formatted as "Gannen" or as a number.</span></span>
- <span data-ttu-id="bcfb1-148">既定:元年を "元年" として書式設定します (`false`)。</span><span class="sxs-lookup"><span data-stu-id="bcfb1-148">Default: Format the first year as "Gannen" (`false`).</span></span>
- <span data-ttu-id="bcfb1-149">詳細については、「[複数の時代 (年号) のカレンダーで日付を表す](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bcfb1-149">For more information, see [Represent dates in calendars with multiple eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span></span>

| | <span data-ttu-id="bcfb1-150">設定の名前</span><span class="sxs-lookup"><span data-stu-id="bcfb1-150">Setting name</span></span> | <span data-ttu-id="bcfb1-151">値</span><span class="sxs-lookup"><span data-stu-id="bcfb1-151">Values</span></span> |
| - | - | - |
| <span data-ttu-id="bcfb1-152">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="bcfb1-152">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.FormatJapaneseFirstYearAsANumber` | <span data-ttu-id="bcfb1-153">`false` - "元年" として書式設定する</span><span class="sxs-lookup"><span data-stu-id="bcfb1-153">`false` - format as "Gannen"</span></span><br/><span data-ttu-id="bcfb1-154">`true` - 数字として書式設定する</span><span class="sxs-lookup"><span data-stu-id="bcfb1-154">`true` - format as number</span></span> |
| <span data-ttu-id="bcfb1-155">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="bcfb1-155">**Environment variable**</span></span> | <span data-ttu-id="bcfb1-156">N/A</span><span class="sxs-lookup"><span data-stu-id="bcfb1-156">N/A</span></span> | <span data-ttu-id="bcfb1-157">N/A</span><span class="sxs-lookup"><span data-stu-id="bcfb1-157">N/A</span></span> |
