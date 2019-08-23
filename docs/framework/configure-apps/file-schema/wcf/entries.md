---
title: <entries>
ms.date: 03/30/2017
ms.assetid: 202e430c-c1b9-4343-abe2-ac78c181a3b7
ms.openlocfilehash: 610ba29ec98f4b1f2a9b1db3542bcb3aefb46457
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925649"
---
# <a name="entries"></a><span data-ttu-id="e55d6-101">\<エントリ ></span><span class="sxs-lookup"><span data-stu-id="e55d6-101">\<entries></span></span>
<span data-ttu-id="e55d6-102">ルーティング フィルターとターゲット エンドポイントとのマッピングを格納するルーティング エントリ。フィルターが一致したときにメッセージを送信するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e55d6-102">A routing entry that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="e55d6-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="e55d6-103">\<system.serviceModel></span></span>  
<span data-ttu-id="e55d6-104">\<ルーティング ></span><span class="sxs-lookup"><span data-stu-id="e55d6-104">\<routing></span></span>  
<span data-ttu-id="e55d6-105">\<routingTables ></span><span class="sxs-lookup"><span data-stu-id="e55d6-105">\<routingTables></span></span>  
<span data-ttu-id="e55d6-106">\<テーブル ></span><span class="sxs-lookup"><span data-stu-id="e55d6-106">\<table></span></span>  
<span data-ttu-id="e55d6-107">\<エントリ ></span><span class="sxs-lookup"><span data-stu-id="e55d6-107">\<entries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e55d6-108">構文</span><span class="sxs-lookup"><span data-stu-id="e55d6-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e55d6-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e55d6-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e55d6-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e55d6-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e55d6-111">属性</span><span class="sxs-lookup"><span data-stu-id="e55d6-111">Attributes</span></span>  
 <span data-ttu-id="e55d6-112">なし。</span><span class="sxs-lookup"><span data-stu-id="e55d6-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e55d6-113">子要素</span><span class="sxs-lookup"><span data-stu-id="e55d6-113">Child Elements</span></span>  
  
|<span data-ttu-id="e55d6-114">要素</span><span class="sxs-lookup"><span data-stu-id="e55d6-114">Element</span></span>|<span data-ttu-id="e55d6-115">説明</span><span class="sxs-lookup"><span data-stu-id="e55d6-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e55d6-116">\<filters></span><span class="sxs-lookup"><span data-stu-id="e55d6-116">\<filters></span></span>](filters-of-routing.md)|<span data-ttu-id="e55d6-117">以前に定義されたクライアント エンドポイントにフィルターをマップします。</span><span class="sxs-lookup"><span data-stu-id="e55d6-117">Maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="e55d6-118">このフィルターに一致するメッセージは、この宛先に送信されます。</span><span class="sxs-lookup"><span data-stu-id="e55d6-118">Messages matching this filter will be sent to this destination.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e55d6-119">親要素</span><span class="sxs-lookup"><span data-stu-id="e55d6-119">Parent Elements</span></span>  
  
|<span data-ttu-id="e55d6-120">要素</span><span class="sxs-lookup"><span data-stu-id="e55d6-120">Element</span></span>|<span data-ttu-id="e55d6-121">説明</span><span class="sxs-lookup"><span data-stu-id="e55d6-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e55d6-122">\<ルーティング ></span><span class="sxs-lookup"><span data-stu-id="e55d6-122">\<routing></span></span>](routing.md)|<span data-ttu-id="e55d6-123">ルーティング テーブルを含む構成セクション。</span><span class="sxs-lookup"><span data-stu-id="e55d6-123">A configuration section that contains a routing table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e55d6-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="e55d6-124">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
