---
title: <EnableAmPmParseAdjustment> 要素
ms.date: 03/30/2017
ms.assetid: fda998a5-f538-4f8b-a18c-ee7f35e16938
ms.openlocfilehash: 8920e51fcaaca5cb78b80a99ea321163c9b5240f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "73117366"
---
# <a name="enableampmparseadjustment-element"></a><span data-ttu-id="34f24-102">\<EnableAmPmParseAdjustment> 要素</span><span class="sxs-lookup"><span data-stu-id="34f24-102">\<EnableAmPmParseAdjustment> Element</span></span>
<span data-ttu-id="34f24-103">日付と時刻の解析メソッドが、日、月、時、および午前/午後の指定子を含む日付文字列を解析するために調整されたルールセットを使用するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="34f24-103">Determines whether date and time parsing methods use an adjusted set of rules to parse date strings that contain a day, month, hour, and AM/PM designator.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<EnableAmPmParseAdjustment>**  
  
## <a name="syntax"></a><span data-ttu-id="34f24-104">構文</span><span class="sxs-lookup"><span data-stu-id="34f24-104">Syntax</span></span>  
  
```xml  
<EnableAmPmParseAdjustment enabled="0"|"1" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="34f24-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="34f24-105">Attributes and Elements</span></span>  
 <span data-ttu-id="34f24-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="34f24-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="34f24-107">属性</span><span class="sxs-lookup"><span data-stu-id="34f24-107">Attributes</span></span>  
  
|<span data-ttu-id="34f24-108">属性</span><span class="sxs-lookup"><span data-stu-id="34f24-108">Attribute</span></span>|<span data-ttu-id="34f24-109">説明</span><span class="sxs-lookup"><span data-stu-id="34f24-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="34f24-110">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="34f24-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="34f24-111">日付と時刻の解析メソッドが、日、月、時、および午前/午後の指定子のみを含む日付文字列を解析するために調整されたルールセットを使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="34f24-111">Specifies whether date and time parsing methods use an adjusted set of rules to parse date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
  
### <a name="enabled-attribute"></a><span data-ttu-id="34f24-112">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="34f24-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="34f24-113">値</span><span class="sxs-lookup"><span data-stu-id="34f24-113">Value</span></span>|<span data-ttu-id="34f24-114">説明</span><span class="sxs-lookup"><span data-stu-id="34f24-114">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="34f24-115">0</span><span class="sxs-lookup"><span data-stu-id="34f24-115">0</span></span>|<span data-ttu-id="34f24-116">日付と時刻の解析メソッドでは、日、月、時、および AM/PM 指定子のみを含む日付文字列を解析するために調整された規則は使用されません。</span><span class="sxs-lookup"><span data-stu-id="34f24-116">Date and time parsing methods do not use adjusted rules for parsing date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
|<span data-ttu-id="34f24-117">1</span><span class="sxs-lookup"><span data-stu-id="34f24-117">1</span></span>|<span data-ttu-id="34f24-118">日付と時刻の解析メソッドでは、日、月、時、および AM/PM 指定子のみを含む日付文字列を解析するための調整された規則が使用されます。</span><span class="sxs-lookup"><span data-stu-id="34f24-118">Date and time parsing methods use adjusted rules for parsing date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="34f24-119">子要素</span><span class="sxs-lookup"><span data-stu-id="34f24-119">Child Elements</span></span>  
 <span data-ttu-id="34f24-120">なし。</span><span class="sxs-lookup"><span data-stu-id="34f24-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="34f24-121">親要素</span><span class="sxs-lookup"><span data-stu-id="34f24-121">Parent Elements</span></span>  
  
|<span data-ttu-id="34f24-122">要素</span><span class="sxs-lookup"><span data-stu-id="34f24-122">Element</span></span>|<span data-ttu-id="34f24-123">Description</span><span class="sxs-lookup"><span data-stu-id="34f24-123">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="34f24-124">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="34f24-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="34f24-125">ランタイム初期化オプションに関する情報を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="34f24-125">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34f24-126">解説</span><span class="sxs-lookup"><span data-stu-id="34f24-126">Remarks</span></span>  
 <span data-ttu-id="34f24-127">要素は、 `<EnableAmPmParseAdjustment>` 次のメソッドが日付文字列を解析する方法を制御します。これには、数字と月の後に1時間と AM/PM 指定子 ("4/10 6 am" など) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="34f24-127">The `<EnableAmPmParseAdjustment>` element controls how the following methods parse a date string that contains a numeric day and month followed by an hour and an AM/PM designator (such as "4/10 6 AM"):</span></span>  
  
- <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTime.TryParse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTimeOffset.TryParse%2A?displayProperty=nameWithType>  
  
- <xref:System.Convert.ToDateTime%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="34f24-128">その他のパターンは影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="34f24-128">No other patterns are affected.</span></span>  
  
 <span data-ttu-id="34f24-129">`<EnableAmPmParseAdjustment>`要素は <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType> 、、、 <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType> 、およびの各 <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType> メソッドには影響しません <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="34f24-129">The `<EnableAmPmParseAdjustment>` element has no effect on the  <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>,  <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>, and <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> methods.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="34f24-130">.NET Core と .NET ネイティブでは、調整された AM/PM 解析規則は既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="34f24-130">In .NET Core and .NET Native, the adjusted AM/PM parsing rules are enabled by default.</span></span>  
  
 <span data-ttu-id="34f24-131">解析調整規則が有効になっていない場合、文字列の最初の桁は12時間形式の時刻として解釈され、AM/PM 指定子を除く文字列の残りの部分は無視されます。</span><span class="sxs-lookup"><span data-stu-id="34f24-131">If the parsing adjustment rule is not enabled, the first digit of the string is interpreted as the hour of the 12-hour clock, and the remainder of the string except for the AM/PM designator is ignored.</span></span> <span data-ttu-id="34f24-132">解析メソッドによって返される日付と時刻は、現在の日付と、日付文字列から抽出された日の時刻で構成されます。</span><span class="sxs-lookup"><span data-stu-id="34f24-132">The date and time returned by the parsing method consists of the current date and the hour of the day extracted from the date string.</span></span>  
  
 <span data-ttu-id="34f24-133">解析の調整規則が有効になっている場合、解析メソッドは、日付と月を現在の年に属するものとして解釈し、時刻を12時間形式の時間として解釈します。</span><span class="sxs-lookup"><span data-stu-id="34f24-133">If the parsing adjustment rule is enabled, parsing method interpret the day and month as belonging to the current year, and interpret the time as the hour of the 12-hour clock.</span></span>  
  
 <span data-ttu-id="34f24-134">次の表は、 <xref:System.DateTime> メソッドを使用して、 <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> `<EnableAmPmParseAdjustment>` 要素の `enabled` プロパティが "0" または "1" に設定された文字列 "" 4/10 6 AM "を解析する場合の値の違いを示しています。</span><span class="sxs-lookup"><span data-stu-id="34f24-134">The following table illustrates the difference in the <xref:System.DateTime> value when the <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> method is used to parse the string ""4/10 6 AM" with the `<EnableAmPmParseAdjustment>` element's `enabled` property  set to "0" or "1".</span></span> <span data-ttu-id="34f24-135">今日の日付が2017年1月5日であると想定し、指定したカルチャの "G" 書式設定文字列を使用して書式設定されているかのように日付を表示します。</span><span class="sxs-lookup"><span data-stu-id="34f24-135">It assumes that today's date is January 5, 2017, and displays the date as if it is formatted using the specified culture's "G" format string.</span></span>  
  
|<span data-ttu-id="34f24-136">カルチャ名</span><span class="sxs-lookup"><span data-stu-id="34f24-136">Culture name</span></span>|<span data-ttu-id="34f24-137">enabled = "0"</span><span class="sxs-lookup"><span data-stu-id="34f24-137">enabled="0"</span></span>|<span data-ttu-id="34f24-138">enabled = "1"</span><span class="sxs-lookup"><span data-stu-id="34f24-138">enabled="1"</span></span>|  
|------------------|------------------|------------------|  
|<span data-ttu-id="34f24-139">ja-JP</span><span class="sxs-lookup"><span data-stu-id="34f24-139">en-US</span></span>|<span data-ttu-id="34f24-140">1/5/2017 4:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="34f24-140">1/5/2017 4:00:00 AM</span></span>|<span data-ttu-id="34f24-141">4/10/2017 6:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="34f24-141">4/10/2017 6:00:00 AM</span></span>|  
|<span data-ttu-id="34f24-142">en-GB</span><span class="sxs-lookup"><span data-stu-id="34f24-142">en-GB</span></span>|<span data-ttu-id="34f24-143">5/1/2017 6:00:00</span><span class="sxs-lookup"><span data-stu-id="34f24-143">5/1/2017 6:00:00</span></span>|<span data-ttu-id="34f24-144">10/4/2017 6:00:00</span><span class="sxs-lookup"><span data-stu-id="34f24-144">10/4/2017 6:00:00</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="34f24-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="34f24-145">See also</span></span>

- [<span data-ttu-id="34f24-146">\<runtime>Element</span><span class="sxs-lookup"><span data-stu-id="34f24-146">\<runtime> Element</span></span>](runtime-element.md)
- [<span data-ttu-id="34f24-147">\<configuration>Element</span><span class="sxs-lookup"><span data-stu-id="34f24-147">\<configuration> Element</span></span>](../configuration-element.md)
