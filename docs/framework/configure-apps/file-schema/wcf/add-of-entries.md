---
title: <add> の <entries>
ms.date: 03/30/2017
ms.assetid: 3af4805b-dc72-4f68-b168-da4fba8c6170
ms.openlocfilehash: 23b0a825ea593f85ade870d5b93367571eaa3ec0
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850510"
---
# <a name="add-of-entries"></a><span data-ttu-id="c29f2-102">\<エントリの > \<を追加 ></span><span class="sxs-lookup"><span data-stu-id="c29f2-102">\<add> of \<entries></span></span>
<span data-ttu-id="c29f2-103">以前に定義されたクライアント エンドポイントにフィルターをマップするルーティング エントリを表します。</span><span class="sxs-lookup"><span data-stu-id="c29f2-103">Represents a routing entry that maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="c29f2-104">このフィルターに一致するメッセージは、この宛先に送信されます。</span><span class="sxs-lookup"><span data-stu-id="c29f2-104">Messages matching this filter will be sent to this destination.</span></span>  
  
<span data-ttu-id="c29f2-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c29f2-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c29f2-106">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="c29f2-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="c29f2-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ルーティング >** ](routing.md)</span><span class="sxs-lookup"><span data-stu-id="c29f2-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="c29f2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<filterTables >** ](filtertables.md)</span><span class="sxs-lookup"><span data-stu-id="c29f2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTables>**](filtertables.md)</span></span>\
<span data-ttu-id="c29f2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<filterTable >** ](filtertable.md)</span><span class="sxs-lookup"><span data-stu-id="c29f2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTable>**](filtertable.md)</span></span>\
<span data-ttu-id="c29f2-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<エントリ >** ](entries.md)</span><span class="sxs-lookup"><span data-stu-id="c29f2-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<entries>**](entries.md)</span></span>\
<span data-ttu-id="c29f2-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> の追加**</span><span class="sxs-lookup"><span data-stu-id="c29f2-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c29f2-112">構文</span><span class="sxs-lookup"><span data-stu-id="c29f2-112">Syntax</span></span>  
  
```xml  
<routing>
  <filterTables>
    <filterTable name="String">
      <entries>
        <add backupList="String"
             endpointName="String"
             filterName="String"
             priority="Integer" />
      </entries>
    </filterTable>
  </filterTables>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c29f2-113">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c29f2-113">Attributes and Elements</span></span>  
 <span data-ttu-id="c29f2-114">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c29f2-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c29f2-115">属性</span><span class="sxs-lookup"><span data-stu-id="c29f2-115">Attributes</span></span>  
  
|<span data-ttu-id="c29f2-116">属性</span><span class="sxs-lookup"><span data-stu-id="c29f2-116">Attribute</span></span>|<span data-ttu-id="c29f2-117">説明</span><span class="sxs-lookup"><span data-stu-id="c29f2-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c29f2-118">backupList</span><span class="sxs-lookup"><span data-stu-id="c29f2-118">backupList</span></span>|<span data-ttu-id="c29f2-119">エンドポイントのバックアップ リストへの参照を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="c29f2-119">A string that specifies a reference to a backup list of endpoints.</span></span>|  
|<span data-ttu-id="c29f2-120">エンドポイント</span><span class="sxs-lookup"><span data-stu-id="c29f2-120">endpoint</span></span>|<span data-ttu-id="c29f2-121">`filterName` 属性で指定されたフィルターに一致するメッセージを受信するクライアント エンドポイントへの参照を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="c29f2-121">A string that specifies a reference to a client endpoint that will receive messages that match the filter specified by the `filterName` attribute.</span></span>|  
|<span data-ttu-id="c29f2-122">filterName</span><span class="sxs-lookup"><span data-stu-id="c29f2-122">filterName</span></span>|<span data-ttu-id="c29f2-123">フィルター要素への参照を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="c29f2-123">A string that specifies a reference to a filter element.</span></span>|  
|<span data-ttu-id="c29f2-124">priority</span><span class="sxs-lookup"><span data-stu-id="c29f2-124">priority</span></span>|<span data-ttu-id="c29f2-125">このエントリの優先順位を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="c29f2-125">An integer that specifies the priority of this entry.</span></span><br /><br /> <span data-ttu-id="c29f2-126">ルーティング テーブルのエントリは、優先順位に基づいて評価されます。0 が最下位の優先順位です。</span><span class="sxs-lookup"><span data-stu-id="c29f2-126">Entries in the routing table will be evaluated based on priority, with 0 being the lowest priority.</span></span> <span data-ttu-id="c29f2-127">特定の優先順位について、すべてのエントリが同時に評価されます。現在の優先順位について一致するエントリが見つからない場合は、次の優先順位が評価されます。</span><span class="sxs-lookup"><span data-stu-id="c29f2-127">All entries for a specific priority are evaluated simultaneously, if no matching entry is found for the current priority, the next priority level will be evaluated.</span></span><br /><br /> <span data-ttu-id="c29f2-128">この値は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="c29f2-128">This value is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c29f2-129">子要素</span><span class="sxs-lookup"><span data-stu-id="c29f2-129">Child Elements</span></span>  
 <span data-ttu-id="c29f2-130">なし。</span><span class="sxs-lookup"><span data-stu-id="c29f2-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c29f2-131">親要素</span><span class="sxs-lookup"><span data-stu-id="c29f2-131">Parent Elements</span></span>  
  
|<span data-ttu-id="c29f2-132">要素</span><span class="sxs-lookup"><span data-stu-id="c29f2-132">Element</span></span>|<span data-ttu-id="c29f2-133">説明</span><span class="sxs-lookup"><span data-stu-id="c29f2-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c29f2-134">\<ルーティング ></span><span class="sxs-lookup"><span data-stu-id="c29f2-134">\<routing></span></span>](routing.md)|<span data-ttu-id="c29f2-135">ルーティング マッピング エントリを含む構成セクション。</span><span class="sxs-lookup"><span data-stu-id="c29f2-135">A configuration section that contains routing mapping entries.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c29f2-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="c29f2-136">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
