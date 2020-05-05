---
title: グローバリゼーションの構成設定
description: .NET Core アプリのグローバリゼーションの側面 (たとえば、日本語の日付の解析方法など) を構成するランタイム設定について説明します。
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 7668c345181d7c08cfca9c5cb76b8addd76223ec
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2020
ms.locfileid: "82506806"
---
# <a name="run-time-configuration-options-for-globalization"></a><span data-ttu-id="fab0b-103">グローバリゼーションのランタイム構成オプション</span><span class="sxs-lookup"><span data-stu-id="fab0b-103">Run-time configuration options for globalization</span></span>

## <a name="invariant-mode"></a><span data-ttu-id="fab0b-104">インバリアント モード</span><span class="sxs-lookup"><span data-stu-id="fab0b-104">Invariant mode</span></span>

- <span data-ttu-id="fab0b-105">.NET Core を、カルチャ固有のデータや動作にアクセスせずにグローバリゼーション インバリアント モードで実行するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="fab0b-105">Determines whether a .NET Core app runs in globalization-invariant mode without access to culture-specific data and behavior.</span></span>
- <span data-ttu-id="fab0b-106">既定:カルチャ データにアクセスしてアプリを実行します (`false`)。</span><span class="sxs-lookup"><span data-stu-id="fab0b-106">Default: Run the app with access to cultural data (`false`).</span></span>
- <span data-ttu-id="fab0b-107">詳細については、「[.NET Core のグローバリゼーション インバリアント モード](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fab0b-107">For more information, see [.NET Core globalization invariant mode](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).</span></span>

| | <span data-ttu-id="fab0b-108">設定の名前</span><span class="sxs-lookup"><span data-stu-id="fab0b-108">Setting name</span></span> | <span data-ttu-id="fab0b-109">値</span><span class="sxs-lookup"><span data-stu-id="fab0b-109">Values</span></span> |
| - | - | - |
| <span data-ttu-id="fab0b-110">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="fab0b-110">**runtimeconfig.json**</span></span> | `System.Globalization.Invariant` | <span data-ttu-id="fab0b-111">`false` - カルチャ データにアクセスする</span><span class="sxs-lookup"><span data-stu-id="fab0b-111">`false` - access to cultural data</span></span><br/><span data-ttu-id="fab0b-112">`true` - インバリアント モードで実行する</span><span class="sxs-lookup"><span data-stu-id="fab0b-112">`true` - run in invariant mode</span></span> |
| <span data-ttu-id="fab0b-113">**MSBuild のプロパティ**</span><span class="sxs-lookup"><span data-stu-id="fab0b-113">**MSBuild property**</span></span> | `InvariantGlobalization` | <span data-ttu-id="fab0b-114">`false` - カルチャ データにアクセスする</span><span class="sxs-lookup"><span data-stu-id="fab0b-114">`false` - access to cultural data</span></span><br/><span data-ttu-id="fab0b-115">`true` - インバリアント モードで実行する</span><span class="sxs-lookup"><span data-stu-id="fab0b-115">`true` - run in invariant mode</span></span> |
| <span data-ttu-id="fab0b-116">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="fab0b-116">**Environment variable**</span></span> | `DOTNET_SYSTEM_GLOBALIZATION_INVARIANT` | <span data-ttu-id="fab0b-117">`0` - カルチャ データにアクセスする</span><span class="sxs-lookup"><span data-stu-id="fab0b-117">`0` - access to cultural data</span></span><br/><span data-ttu-id="fab0b-118">`1` - インバリアント モードで実行する</span><span class="sxs-lookup"><span data-stu-id="fab0b-118">`1` - run in invariant mode</span></span> |

### <a name="examples"></a><span data-ttu-id="fab0b-119">使用例</span><span class="sxs-lookup"><span data-stu-id="fab0b-119">Examples</span></span>

<span data-ttu-id="fab0b-120">*runtimeconfig.json* ファイル:</span><span class="sxs-lookup"><span data-stu-id="fab0b-120">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Globalization.Invariant": true
      }
   }
}
```

<span data-ttu-id="fab0b-121">プロジェクト ファイル:</span><span class="sxs-lookup"><span data-stu-id="fab0b-121">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <InvariantGlobalization>true</InvariantGlobalization>
  </PropertyGroup>

</Project>
```

## <a name="era-year-ranges"></a><span data-ttu-id="fab0b-122">年号の範囲</span><span class="sxs-lookup"><span data-stu-id="fab0b-122">Era year ranges</span></span>

- <span data-ttu-id="fab0b-123">複数の年号をサポートするカレンダーの範囲チェックを緩和するか、または日付が年号の日付範囲をオーバーフローした場合に <xref:System.ArgumentOutOfRangeException> をスローするかを決定します。</span><span class="sxs-lookup"><span data-stu-id="fab0b-123">Determines whether range checks for calendars that support multiple eras are relaxed or whether dates that overflow an era's date range throw an <xref:System.ArgumentOutOfRangeException>.</span></span>
- <span data-ttu-id="fab0b-124">既定:範囲チェックを緩和します (`false`)。</span><span class="sxs-lookup"><span data-stu-id="fab0b-124">Default: Range checks are relaxed (`false`).</span></span>
- <span data-ttu-id="fab0b-125">詳細については、「[カレンダー、時代 (年号)、および日付範囲: 緩やかな範囲のチェック](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fab0b-125">For more information, see [Calendars, eras, and date ranges: Relaxed range checks](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks).</span></span>

| | <span data-ttu-id="fab0b-126">設定の名前</span><span class="sxs-lookup"><span data-stu-id="fab0b-126">Setting name</span></span> | <span data-ttu-id="fab0b-127">値</span><span class="sxs-lookup"><span data-stu-id="fab0b-127">Values</span></span> |
| - | - | - |
| <span data-ttu-id="fab0b-128">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="fab0b-128">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.EnforceJapaneseEraYearRanges` | <span data-ttu-id="fab0b-129">`false` - 緩和された範囲チェック</span><span class="sxs-lookup"><span data-stu-id="fab0b-129">`false` - relaxed range checks</span></span><br/><span data-ttu-id="fab0b-130">`true` - オーバーフローによって例外が発生する</span><span class="sxs-lookup"><span data-stu-id="fab0b-130">`true` - overflows cause an exception</span></span> |
| <span data-ttu-id="fab0b-131">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="fab0b-131">**Environment variable**</span></span> | <span data-ttu-id="fab0b-132">N/A</span><span class="sxs-lookup"><span data-stu-id="fab0b-132">N/A</span></span> | <span data-ttu-id="fab0b-133">N/A</span><span class="sxs-lookup"><span data-stu-id="fab0b-133">N/A</span></span> |

## <a name="japanese-date-parsing"></a><span data-ttu-id="fab0b-134">日本の日付の解析</span><span class="sxs-lookup"><span data-stu-id="fab0b-134">Japanese date parsing</span></span>

- <span data-ttu-id="fab0b-135">年として "1" または "元年" のいずれかを含む文字列を正しく解析するか、または "1" のみをサポートするかを決定します。</span><span class="sxs-lookup"><span data-stu-id="fab0b-135">Determines whether a string that contains either "1" or "Gannen" as the year parses successfully or whether only "1" is supported.</span></span>
- <span data-ttu-id="fab0b-136">既定:"1" または "元年" のいずれかを含む文字列を年として解析します (`false`)。</span><span class="sxs-lookup"><span data-stu-id="fab0b-136">Default: Parse strings that contain either "1" or "Gannen" as the year (`false`).</span></span>
- <span data-ttu-id="fab0b-137">詳細については、「[複数の時代 (年号) のカレンダーで日付を表す](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fab0b-137">For more information, see [Represent dates in calendars with multiple eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span></span>

| | <span data-ttu-id="fab0b-138">設定の名前</span><span class="sxs-lookup"><span data-stu-id="fab0b-138">Setting name</span></span> | <span data-ttu-id="fab0b-139">値</span><span class="sxs-lookup"><span data-stu-id="fab0b-139">Values</span></span> |
| - | - | - |
| <span data-ttu-id="fab0b-140">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="fab0b-140">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.EnforceLegacyJapaneseDateParsing` | <span data-ttu-id="fab0b-141">`false` - "元年" または "1" をサポートする</span><span class="sxs-lookup"><span data-stu-id="fab0b-141">`false` - "Gannen" or "1" is supported</span></span><br/><span data-ttu-id="fab0b-142">`true` - "1" のみをサポートする</span><span class="sxs-lookup"><span data-stu-id="fab0b-142">`true` - only "1" is supported</span></span> |
| <span data-ttu-id="fab0b-143">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="fab0b-143">**Environment variable**</span></span> | <span data-ttu-id="fab0b-144">N/A</span><span class="sxs-lookup"><span data-stu-id="fab0b-144">N/A</span></span> | <span data-ttu-id="fab0b-145">N/A</span><span class="sxs-lookup"><span data-stu-id="fab0b-145">N/A</span></span> |

## <a name="japanese-year-format"></a><span data-ttu-id="fab0b-146">日本の年の形式</span><span class="sxs-lookup"><span data-stu-id="fab0b-146">Japanese year format</span></span>

- <span data-ttu-id="fab0b-147">和暦の元年を "元年" または "1" のどちらで書式設定するかを決定します。</span><span class="sxs-lookup"><span data-stu-id="fab0b-147">Determines whether the first year of a Japanese calendar era is formatted as "Gannen" or as a number.</span></span>
- <span data-ttu-id="fab0b-148">既定:元年を "元年" として書式設定します (`false`)。</span><span class="sxs-lookup"><span data-stu-id="fab0b-148">Default: Format the first year as "Gannen" (`false`).</span></span>
- <span data-ttu-id="fab0b-149">詳細については、「[複数の時代 (年号) のカレンダーで日付を表す](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fab0b-149">For more information, see [Represent dates in calendars with multiple eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span></span>

| | <span data-ttu-id="fab0b-150">設定の名前</span><span class="sxs-lookup"><span data-stu-id="fab0b-150">Setting name</span></span> | <span data-ttu-id="fab0b-151">値</span><span class="sxs-lookup"><span data-stu-id="fab0b-151">Values</span></span> |
| - | - | - |
| <span data-ttu-id="fab0b-152">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="fab0b-152">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.FormatJapaneseFirstYearAsANumber` | <span data-ttu-id="fab0b-153">`false` - "元年" として書式設定する</span><span class="sxs-lookup"><span data-stu-id="fab0b-153">`false` - format as "Gannen"</span></span><br/><span data-ttu-id="fab0b-154">`true` - 数字として書式設定する</span><span class="sxs-lookup"><span data-stu-id="fab0b-154">`true` - format as number</span></span> |
| <span data-ttu-id="fab0b-155">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="fab0b-155">**Environment variable**</span></span> | <span data-ttu-id="fab0b-156">N/A</span><span class="sxs-lookup"><span data-stu-id="fab0b-156">N/A</span></span> | <span data-ttu-id="fab0b-157">N/A</span><span class="sxs-lookup"><span data-stu-id="fab0b-157">N/A</span></span> |
