---
title: <add> の <entries>
ms.date: 03/30/2017
ms.assetid: 3af4805b-dc72-4f68-b168-da4fba8c6170
ms.openlocfilehash: 23b0a825ea593f85ade870d5b93367571eaa3ec0
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850510"
---
# <a name="add-of-entries"></a><span data-ttu-id="b081e-102">\<add> の \<entries></span><span class="sxs-lookup"><span data-stu-id="b081e-102">\<add> of \<entries></span></span>
<span data-ttu-id="b081e-103">以前に定義されたクライアント エンドポイントにフィルターをマップするルーティング エントリを表します。</span><span class="sxs-lookup"><span data-stu-id="b081e-103">Represents a routing entry that maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="b081e-104">このフィルターに一致するメッセージは、この宛先に送信されます。</span><span class="sxs-lookup"><span data-stu-id="b081e-104">Messages matching this filter will be sent to this destination.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTables>**](filtertables.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTable>**](filtertable.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<entries>**](entries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="b081e-105">構文</span><span class="sxs-lookup"><span data-stu-id="b081e-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b081e-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b081e-106">Attributes and Elements</span></span>  
 <span data-ttu-id="b081e-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b081e-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b081e-108">属性</span><span class="sxs-lookup"><span data-stu-id="b081e-108">Attributes</span></span>  
  
|<span data-ttu-id="b081e-109">属性</span><span class="sxs-lookup"><span data-stu-id="b081e-109">Attribute</span></span>|<span data-ttu-id="b081e-110">説明</span><span class="sxs-lookup"><span data-stu-id="b081e-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b081e-111">backupList</span><span class="sxs-lookup"><span data-stu-id="b081e-111">backupList</span></span>|<span data-ttu-id="b081e-112">エンドポイントのバックアップ リストへの参照を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="b081e-112">A string that specifies a reference to a backup list of endpoints.</span></span>|  
|<span data-ttu-id="b081e-113">endpoint</span><span class="sxs-lookup"><span data-stu-id="b081e-113">endpoint</span></span>|<span data-ttu-id="b081e-114">`filterName` 属性で指定されたフィルターに一致するメッセージを受信するクライアント エンドポイントへの参照を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="b081e-114">A string that specifies a reference to a client endpoint that will receive messages that match the filter specified by the `filterName` attribute.</span></span>|  
|<span data-ttu-id="b081e-115">filterName</span><span class="sxs-lookup"><span data-stu-id="b081e-115">filterName</span></span>|<span data-ttu-id="b081e-116">フィルター要素への参照を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="b081e-116">A string that specifies a reference to a filter element.</span></span>|  
|<span data-ttu-id="b081e-117">priority</span><span class="sxs-lookup"><span data-stu-id="b081e-117">priority</span></span>|<span data-ttu-id="b081e-118">このエントリの優先順位を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="b081e-118">An integer that specifies the priority of this entry.</span></span><br /><br /> <span data-ttu-id="b081e-119">ルーティング テーブルのエントリは、優先順位に基づいて評価されます。0 が最下位の優先順位です。</span><span class="sxs-lookup"><span data-stu-id="b081e-119">Entries in the routing table will be evaluated based on priority, with 0 being the lowest priority.</span></span> <span data-ttu-id="b081e-120">特定の優先順位について、すべてのエントリが同時に評価されます。現在の優先順位について一致するエントリが見つからない場合は、次の優先順位が評価されます。</span><span class="sxs-lookup"><span data-stu-id="b081e-120">All entries for a specific priority are evaluated simultaneously, if no matching entry is found for the current priority, the next priority level will be evaluated.</span></span><br /><br /> <span data-ttu-id="b081e-121">この値は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="b081e-121">This value is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b081e-122">子要素</span><span class="sxs-lookup"><span data-stu-id="b081e-122">Child Elements</span></span>  
 <span data-ttu-id="b081e-123">なし。</span><span class="sxs-lookup"><span data-stu-id="b081e-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b081e-124">親要素</span><span class="sxs-lookup"><span data-stu-id="b081e-124">Parent Elements</span></span>  
  
|<span data-ttu-id="b081e-125">要素</span><span class="sxs-lookup"><span data-stu-id="b081e-125">Element</span></span>|<span data-ttu-id="b081e-126">Description</span><span class="sxs-lookup"><span data-stu-id="b081e-126">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="b081e-127">ルーティング マッピング エントリを含む構成セクション。</span><span class="sxs-lookup"><span data-stu-id="b081e-127">A configuration section that contains routing mapping entries.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b081e-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="b081e-128">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
