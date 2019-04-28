---
title: <EnableAmPmParseAdjustment> 要素
ms.date: 03/30/2017
ms.assetid: fda998a5-f538-4f8b-a18c-ee7f35e16938
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 57d1a14199debbb90827c1ea95347d485a636329
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704844"
---
# <a name="enableampmparseadjustment-element"></a><span data-ttu-id="1dfac-102">\<EnableAmPmParseAdjustment > 要素</span><span class="sxs-lookup"><span data-stu-id="1dfac-102">\<EnableAmPmParseAdjustment> Element</span></span>
<span data-ttu-id="1dfac-103">日付と時刻の解析メソッドが日、月、1 時間、および AM/PM 指定子を含む日付の文字列を解析する調整済みの一連のルールを使用しているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="1dfac-103">Determines whether date and time parsing methods use an adjusted set of rules to parse date strings that contain a day, month, hour, and AM/PM designator.</span></span>  
  
 <span data-ttu-id="1dfac-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="1dfac-104">\<configuration></span></span>  
 <span data-ttu-id="1dfac-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="1dfac-105">\<runtime></span></span>  
<span data-ttu-id="1dfac-106">\<EnableAmPmParseAdjustment></span><span class="sxs-lookup"><span data-stu-id="1dfac-106">\<EnableAmPmParseAdjustment></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1dfac-107">構文</span><span class="sxs-lookup"><span data-stu-id="1dfac-107">Syntax</span></span>  
  
```xml  
<EnableAmPmParseAdjustment enabled="0"|"1" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1dfac-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1dfac-108">Attributes and Elements</span></span>  
 <span data-ttu-id="1dfac-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1dfac-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1dfac-110">属性</span><span class="sxs-lookup"><span data-stu-id="1dfac-110">Attributes</span></span>  
  
|<span data-ttu-id="1dfac-111">属性</span><span class="sxs-lookup"><span data-stu-id="1dfac-111">Attribute</span></span>|<span data-ttu-id="1dfac-112">説明</span><span class="sxs-lookup"><span data-stu-id="1dfac-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="1dfac-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="1dfac-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="1dfac-114">日付と時刻の解析メソッドで、日、月、時、午前/午後のみを含む日付の文字列を解析する調整済みの一連のルールを使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="1dfac-114">Specifies whether date and time parsing methods use an adjusted set of rules to parse date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
  
### <a name="enabled-attribute"></a><span data-ttu-id="1dfac-115">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="1dfac-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="1dfac-116">値</span><span class="sxs-lookup"><span data-stu-id="1dfac-116">Value</span></span>|<span data-ttu-id="1dfac-117">説明</span><span class="sxs-lookup"><span data-stu-id="1dfac-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1dfac-118">0</span><span class="sxs-lookup"><span data-stu-id="1dfac-118">0</span></span>|<span data-ttu-id="1dfac-119">日付と時刻の解析メソッドを日、月、時、午前/午後のみを含む日付の文字列を解析するため調整済みの規則を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="1dfac-119">Date and time parsing methods do not use adjusted rules for parsing date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
|<span data-ttu-id="1dfac-120">1</span><span class="sxs-lookup"><span data-stu-id="1dfac-120">1</span></span>|<span data-ttu-id="1dfac-121">日付と時刻の解析メソッドは、調整済みの規則を使用して、日、月、時、午前/午後のみを含む日付文字列を解析するため。</span><span class="sxs-lookup"><span data-stu-id="1dfac-121">Date and time parsing methods use adjusted rules for parsing date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1dfac-122">子要素</span><span class="sxs-lookup"><span data-stu-id="1dfac-122">Child Elements</span></span>  
 <span data-ttu-id="1dfac-123">なし。</span><span class="sxs-lookup"><span data-stu-id="1dfac-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1dfac-124">親要素</span><span class="sxs-lookup"><span data-stu-id="1dfac-124">Parent Elements</span></span>  
  
|<span data-ttu-id="1dfac-125">要素</span><span class="sxs-lookup"><span data-stu-id="1dfac-125">Element</span></span>|<span data-ttu-id="1dfac-126">説明</span><span class="sxs-lookup"><span data-stu-id="1dfac-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="1dfac-127">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="1dfac-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="1dfac-128">ランタイム初期化オプションに関する情報を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="1dfac-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1dfac-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="1dfac-129">Remarks</span></span>  
 <span data-ttu-id="1dfac-130">`<EnableAmPmParseAdjustment>`要素は、次のメソッドが 1 日と月の後に 1 時間と、AM/PM 指定子 (「10 4/6 AM」) などを含む日付文字列を解析する方法を制御します。</span><span class="sxs-lookup"><span data-stu-id="1dfac-130">The `<EnableAmPmParseAdjustment>` element controls how the following methods parse a date string that contains a numeric day and month followed by an hour and an AM/PM designator (such as "4/10 6 AM"):</span></span>  
  
- <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTime.TryParse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTimeOffset.TryParse%2A?displayProperty=nameWithType>  
  
- <xref:System.Convert.ToDateTime%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="1dfac-131">その他のパターンが影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="1dfac-131">No other patterns are affected.</span></span>  
  
 <span data-ttu-id="1dfac-132">`<EnableAmPmParseAdjustment>`要素も何も起こりません、 <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>、 <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>、 <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>、および<xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType>メソッド。</span><span class="sxs-lookup"><span data-stu-id="1dfac-132">The `<EnableAmPmParseAdjustment>` element has no effect on the  <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>,  <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>, and <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> methods.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1dfac-133">.NET Core と .NET ネイティブでは、調整済みの午前/午後解析規則は既定で有効にします。</span><span class="sxs-lookup"><span data-stu-id="1dfac-133">In .NET Core and .NET Native, the adjusted AM/PM parsing rules are enabled by default.</span></span>  
  
 <span data-ttu-id="1dfac-134">解析の調整規則が有効でない場合は、文字列の最初の桁は、12 時間時計の時間として解釈され、午前/午後を除く、文字列の残りの部分は無視されます。</span><span class="sxs-lookup"><span data-stu-id="1dfac-134">If the parsing adjustment rule is not enabled, the first digit of the string is interpreted as the hour of the 12-hour clock, and the remainder of the string except for the AM/PM designator is ignored.</span></span> <span data-ttu-id="1dfac-135">日付と時刻の解析メソッドによって返されるは、現在の日付と日付の文字列から抽出された日の時間で構成されます。</span><span class="sxs-lookup"><span data-stu-id="1dfac-135">The date and time returned by the parsing method consists of the current date and the hour of the day extracted from the date string.</span></span>  
  
 <span data-ttu-id="1dfac-136">解析の調整規則が有効になっている場合はメソッドの解析、現在の年に属するものとして月と日を解釈し、12 時間制の時間で時間を解釈します。</span><span class="sxs-lookup"><span data-stu-id="1dfac-136">If the parsing adjustment rule is enabled, parsing method interpret the day and month as belonging to the current year, and interpret the time as the hour of the 12-hour clock.</span></span>  
  
 <span data-ttu-id="1dfac-137">次の表の違いを示しています、<xref:System.DateTime>ときの値、<xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType>メソッドは、文字列の解析に使用される"「10 4/6 AM」、`<EnableAmPmParseAdjustment>`要素の`enabled`プロパティが「0」または「1」に設定します。</span><span class="sxs-lookup"><span data-stu-id="1dfac-137">The following table illustrates the difference in the <xref:System.DateTime> value when the <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> method is used to parse the string ""4/10 6 AM" with the `<EnableAmPmParseAdjustment>` element's `enabled` property  set to "0" or "1".</span></span> <span data-ttu-id="1dfac-138">今日の日付が 2017 年 1 月 5 日し、日付が表示されますが、指定したカルチャの"G"書式指定文字列を使用して書式設定された場合と前提としています。</span><span class="sxs-lookup"><span data-stu-id="1dfac-138">It assumes that today's date is January 5, 2017, and displays the date as if it is formatted using the specified culture's "G" format string.</span></span>  
  
|<span data-ttu-id="1dfac-139">カルチャ名</span><span class="sxs-lookup"><span data-stu-id="1dfac-139">Culture name</span></span>|<span data-ttu-id="1dfac-140">有効になっている =「0」</span><span class="sxs-lookup"><span data-stu-id="1dfac-140">enabled="0"</span></span>|<span data-ttu-id="1dfac-141">enabled="1"</span><span class="sxs-lookup"><span data-stu-id="1dfac-141">enabled="1"</span></span>|  
|------------------|------------------|------------------|  
|<span data-ttu-id="1dfac-142">en-US</span><span class="sxs-lookup"><span data-stu-id="1dfac-142">en-US</span></span>|<span data-ttu-id="1dfac-143">2017 年 1 月 5 4時 00分: 00 AM</span><span class="sxs-lookup"><span data-stu-id="1dfac-143">1/5/2017 4:00:00 AM</span></span>|<span data-ttu-id="1dfac-144">2017 年 4 月 10 6時 00分: 00 AM</span><span class="sxs-lookup"><span data-stu-id="1dfac-144">4/10/2017 6:00:00 AM</span></span>|  
|<span data-ttu-id="1dfac-145">en-GB</span><span class="sxs-lookup"><span data-stu-id="1dfac-145">en-GB</span></span>|<span data-ttu-id="1dfac-146">5/1/2017 6:00:00</span><span class="sxs-lookup"><span data-stu-id="1dfac-146">5/1/2017 6:00:00</span></span>|<span data-ttu-id="1dfac-147">10/4/2017 6:00:00</span><span class="sxs-lookup"><span data-stu-id="1dfac-147">10/4/2017 6:00:00</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1dfac-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="1dfac-148">See also</span></span>

- [<span data-ttu-id="1dfac-149">\<ランタイム > 要素</span><span class="sxs-lookup"><span data-stu-id="1dfac-149">\<runtime> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)
- [<span data-ttu-id="1dfac-150">\<configuration> 要素</span><span class="sxs-lookup"><span data-stu-id="1dfac-150">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)
