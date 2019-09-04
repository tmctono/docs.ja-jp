---
title: <EnableAmPmParseAdjustment> 要素
ms.date: 03/30/2017
ms.assetid: fda998a5-f538-4f8b-a18c-ee7f35e16938
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f132ce0a114a6fc904d86ca3ce893c447366523f
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252625"
---
# <a name="enableampmparseadjustment-element"></a><span data-ttu-id="08478-102">\<EnableAmPmParseAdjustment > 要素</span><span class="sxs-lookup"><span data-stu-id="08478-102">\<EnableAmPmParseAdjustment> Element</span></span>
<span data-ttu-id="08478-103">日付と時刻の解析メソッドが、日、月、時、および午前/午後の指定子を含む日付文字列を解析するために調整されたルールセットを使用するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="08478-103">Determines whether date and time parsing methods use an adjusted set of rules to parse date strings that contain a day, month, hour, and AM/PM designator.</span></span>  
  
<span data-ttu-id="08478-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="08478-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="08478-105">&nbsp;&nbsp;[ **\<ランタイム >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="08478-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="08478-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<EnableAmPmParseAdjustment>**</span><span class="sxs-lookup"><span data-stu-id="08478-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<EnableAmPmParseAdjustment>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08478-107">構文</span><span class="sxs-lookup"><span data-stu-id="08478-107">Syntax</span></span>  
  
```xml  
<EnableAmPmParseAdjustment enabled="0"|"1" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="08478-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="08478-108">Attributes and Elements</span></span>  
 <span data-ttu-id="08478-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="08478-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="08478-110">属性</span><span class="sxs-lookup"><span data-stu-id="08478-110">Attributes</span></span>  
  
|<span data-ttu-id="08478-111">属性</span><span class="sxs-lookup"><span data-stu-id="08478-111">Attribute</span></span>|<span data-ttu-id="08478-112">説明</span><span class="sxs-lookup"><span data-stu-id="08478-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="08478-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="08478-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="08478-114">日付と時刻の解析メソッドが、日、月、時、および午前/午後の指定子のみを含む日付文字列を解析するために調整されたルールセットを使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="08478-114">Specifies whether date and time parsing methods use an adjusted set of rules to parse date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
  
### <a name="enabled-attribute"></a><span data-ttu-id="08478-115">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="08478-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="08478-116">値</span><span class="sxs-lookup"><span data-stu-id="08478-116">Value</span></span>|<span data-ttu-id="08478-117">説明</span><span class="sxs-lookup"><span data-stu-id="08478-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="08478-118">0</span><span class="sxs-lookup"><span data-stu-id="08478-118">0</span></span>|<span data-ttu-id="08478-119">日付と時刻の解析メソッドでは、日、月、時、および AM/PM 指定子のみを含む日付文字列を解析するために調整された規則は使用されません。</span><span class="sxs-lookup"><span data-stu-id="08478-119">Date and time parsing methods do not use adjusted rules for parsing date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
|<span data-ttu-id="08478-120">1</span><span class="sxs-lookup"><span data-stu-id="08478-120">1</span></span>|<span data-ttu-id="08478-121">日付と時刻の解析メソッドでは、日、月、時、および AM/PM 指定子のみを含む日付文字列を解析するための調整された規則が使用されます。</span><span class="sxs-lookup"><span data-stu-id="08478-121">Date and time parsing methods use adjusted rules for parsing date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="08478-122">子要素</span><span class="sxs-lookup"><span data-stu-id="08478-122">Child Elements</span></span>  
 <span data-ttu-id="08478-123">なし。</span><span class="sxs-lookup"><span data-stu-id="08478-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="08478-124">親要素</span><span class="sxs-lookup"><span data-stu-id="08478-124">Parent Elements</span></span>  
  
|<span data-ttu-id="08478-125">要素</span><span class="sxs-lookup"><span data-stu-id="08478-125">Element</span></span>|<span data-ttu-id="08478-126">説明</span><span class="sxs-lookup"><span data-stu-id="08478-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="08478-127">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="08478-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="08478-128">ランタイム初期化オプションに関する情報を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="08478-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="08478-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="08478-129">Remarks</span></span>  
 <span data-ttu-id="08478-130">要素`<EnableAmPmParseAdjustment>`は、次のメソッドが日付文字列を解析する方法を制御します。これには、数字と月の後に1時間と AM/PM 指定子 ("4/10 6 am" など) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="08478-130">The `<EnableAmPmParseAdjustment>` element controls how the following methods parse a date string that contains a numeric day and month followed by an hour and an AM/PM designator (such as "4/10 6 AM"):</span></span>  
  
- <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTime.TryParse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTimeOffset.TryParse%2A?displayProperty=nameWithType>  
  
- <xref:System.Convert.ToDateTime%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="08478-131">その他のパターンは影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="08478-131">No other patterns are affected.</span></span>  
  
 <span data-ttu-id="08478-132">要素`<EnableAmPmParseAdjustment>` <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>は、、 <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>、、および<xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType>の各メソッドには影響しません。 <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="08478-132">The `<EnableAmPmParseAdjustment>` element has no effect on the  <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>,  <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>, and <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> methods.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="08478-133">.NET Core と .NET ネイティブでは、調整された AM/PM 解析規則は既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="08478-133">In .NET Core and .NET Native, the adjusted AM/PM parsing rules are enabled by default.</span></span>  
  
 <span data-ttu-id="08478-134">解析調整規則が有効になっていない場合、文字列の最初の桁は12時間形式の時刻として解釈され、AM/PM 指定子を除く文字列の残りの部分は無視されます。</span><span class="sxs-lookup"><span data-stu-id="08478-134">If the parsing adjustment rule is not enabled, the first digit of the string is interpreted as the hour of the 12-hour clock, and the remainder of the string except for the AM/PM designator is ignored.</span></span> <span data-ttu-id="08478-135">解析メソッドによって返される日付と時刻は、現在の日付と、日付文字列から抽出された日の時刻で構成されます。</span><span class="sxs-lookup"><span data-stu-id="08478-135">The date and time returned by the parsing method consists of the current date and the hour of the day extracted from the date string.</span></span>  
  
 <span data-ttu-id="08478-136">解析の調整規則が有効になっている場合、解析メソッドは、日付と月を現在の年に属するものとして解釈し、時刻を12時間形式の時間として解釈します。</span><span class="sxs-lookup"><span data-stu-id="08478-136">If the parsing adjustment rule is enabled, parsing method interpret the day and month as belonging to the current year, and interpret the time as the hour of the 12-hour clock.</span></span>  
  
 <span data-ttu-id="08478-137">次の表は、メソッドを使用<xref:System.DateTime>し<xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType>て、 `<EnableAmPmParseAdjustment>`要素の`enabled`プロパティが "0" または "1" に設定された文字列 "" 4/10 6 AM "を解析する場合の値の違いを示しています。</span><span class="sxs-lookup"><span data-stu-id="08478-137">The following table illustrates the difference in the <xref:System.DateTime> value when the <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> method is used to parse the string ""4/10 6 AM" with the `<EnableAmPmParseAdjustment>` element's `enabled` property  set to "0" or "1".</span></span> <span data-ttu-id="08478-138">今日の日付が2017年1月5日であると想定し、指定したカルチャの "G" 書式設定文字列を使用して書式設定されているかのように日付を表示します。</span><span class="sxs-lookup"><span data-stu-id="08478-138">It assumes that today's date is January 5, 2017, and displays the date as if it is formatted using the specified culture's "G" format string.</span></span>  
  
|<span data-ttu-id="08478-139">カルチャ名</span><span class="sxs-lookup"><span data-stu-id="08478-139">Culture name</span></span>|<span data-ttu-id="08478-140">enabled = "0"</span><span class="sxs-lookup"><span data-stu-id="08478-140">enabled="0"</span></span>|<span data-ttu-id="08478-141">enabled = "1"</span><span class="sxs-lookup"><span data-stu-id="08478-141">enabled="1"</span></span>|  
|------------------|------------------|------------------|  
|<span data-ttu-id="08478-142">en-US</span><span class="sxs-lookup"><span data-stu-id="08478-142">en-US</span></span>|<span data-ttu-id="08478-143">1/5/2017 4:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="08478-143">1/5/2017 4:00:00 AM</span></span>|<span data-ttu-id="08478-144">4/10/2017 6:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="08478-144">4/10/2017 6:00:00 AM</span></span>|  
|<span data-ttu-id="08478-145">en-GB</span><span class="sxs-lookup"><span data-stu-id="08478-145">en-GB</span></span>|<span data-ttu-id="08478-146">5/1/2017 6:00:00</span><span class="sxs-lookup"><span data-stu-id="08478-146">5/1/2017 6:00:00</span></span>|<span data-ttu-id="08478-147">10/4/2017 6:00:00</span><span class="sxs-lookup"><span data-stu-id="08478-147">10/4/2017 6:00:00</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="08478-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="08478-148">See also</span></span>

- [<span data-ttu-id="08478-149">\<runtime> 要素</span><span class="sxs-lookup"><span data-stu-id="08478-149">\<runtime> Element</span></span>](runtime-element.md)
- [<span data-ttu-id="08478-150">\<configuration> 要素</span><span class="sxs-lookup"><span data-stu-id="08478-150">\<configuration> Element</span></span>](../configuration-element.md)
