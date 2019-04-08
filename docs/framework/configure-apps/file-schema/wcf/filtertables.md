---
title: <filterTables>
ms.date: 03/30/2017
ms.assetid: 41f1ac35-f559-473a-b2c3-8cc83a6a3831
ms.openlocfilehash: c49c7cf3a196595556c2bf1b4ed4365bfe1e4cbf
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59075731"
---
# <a name="filtertables"></a><span data-ttu-id="dfe44-101">\<filterTables></span><span class="sxs-lookup"><span data-stu-id="dfe44-101">\<filterTables></span></span>
<span data-ttu-id="dfe44-102">ルーティング フィルターとターゲット エンドポイントとのマッピングを格納するルーティング テーブルを定義する構成セクションを表します。フィルターが一致したときにメッセージを送信するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="dfe44-102">Represents a configuration section for defining routing tables that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="dfe44-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="dfe44-103">\<system.serviceModel></span></span>  
<span data-ttu-id="dfe44-104">\<ルーティング ></span><span class="sxs-lookup"><span data-stu-id="dfe44-104">\<routing></span></span>  
<span data-ttu-id="dfe44-105">\<routingTables></span><span class="sxs-lookup"><span data-stu-id="dfe44-105">\<routingTables></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfe44-106">構文</span><span class="sxs-lookup"><span data-stu-id="dfe44-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dfe44-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="dfe44-107">Attributes and Elements</span></span>  
 <span data-ttu-id="dfe44-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="dfe44-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dfe44-109">属性</span><span class="sxs-lookup"><span data-stu-id="dfe44-109">Attributes</span></span>  
 <span data-ttu-id="dfe44-110">なし。</span><span class="sxs-lookup"><span data-stu-id="dfe44-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="dfe44-111">子要素</span><span class="sxs-lookup"><span data-stu-id="dfe44-111">Child Elements</span></span>  
  
|<span data-ttu-id="dfe44-112">要素</span><span class="sxs-lookup"><span data-stu-id="dfe44-112">Element</span></span>|<span data-ttu-id="dfe44-113">説明</span><span class="sxs-lookup"><span data-stu-id="dfe44-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dfe44-114">\<filters></span><span class="sxs-lookup"><span data-stu-id="dfe44-114">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="dfe44-115">ルーティング フィルターとターゲット エンドポイントとのマッピングを格納するルーティング テーブル。フィルターが一致したときにメッセージを送信するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="dfe44-115">A routing table that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dfe44-116">親要素</span><span class="sxs-lookup"><span data-stu-id="dfe44-116">Parent Elements</span></span>  
  
|<span data-ttu-id="dfe44-117">要素</span><span class="sxs-lookup"><span data-stu-id="dfe44-117">Element</span></span>|<span data-ttu-id="dfe44-118">説明</span><span class="sxs-lookup"><span data-stu-id="dfe44-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dfe44-119">\<ルーティング ></span><span class="sxs-lookup"><span data-stu-id="dfe44-119">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="dfe44-120">ルーティング フィルターおよびルーティング テーブルを含む構成セクション。</span><span class="sxs-lookup"><span data-stu-id="dfe44-120">A configuration section that contains routing filters and routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dfe44-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="dfe44-121">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableCollection?displayProperty=nameWithType>
