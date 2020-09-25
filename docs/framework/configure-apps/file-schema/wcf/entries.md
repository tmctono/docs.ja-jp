---
title: <entries>
ms.date: 03/30/2017
ms.assetid: 202e430c-c1b9-4343-abe2-ac78c181a3b7
ms.openlocfilehash: d3dae510ac62735138a24b8fb97a8acfffde1a98
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189969"
---
# \<entries>

<span data-ttu-id="1fbb9-101">ルーティング フィルターとターゲット エンドポイントとのマッピングを格納するルーティング エントリ。フィルターが一致したときにメッセージを送信するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="1fbb9-101">A routing entry that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTables>**](filtertables.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTable>**](filtertable.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<entries>**  
  
## <a name="syntax"></a><span data-ttu-id="1fbb9-102">構文</span><span class="sxs-lookup"><span data-stu-id="1fbb9-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1fbb9-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1fbb9-103">Attributes and Elements</span></span>  

 <span data-ttu-id="1fbb9-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1fbb9-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1fbb9-105">属性</span><span class="sxs-lookup"><span data-stu-id="1fbb9-105">Attributes</span></span>  

 <span data-ttu-id="1fbb9-106">なし。</span><span class="sxs-lookup"><span data-stu-id="1fbb9-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1fbb9-107">子要素</span><span class="sxs-lookup"><span data-stu-id="1fbb9-107">Child Elements</span></span>  
  
|<span data-ttu-id="1fbb9-108">要素</span><span class="sxs-lookup"><span data-stu-id="1fbb9-108">Element</span></span>|<span data-ttu-id="1fbb9-109">説明</span><span class="sxs-lookup"><span data-stu-id="1fbb9-109">Description</span></span>|  
|-------------|-----------------|  
|[\<filters>](filters-of-routing.md)|<span data-ttu-id="1fbb9-110">以前に定義されたクライアント エンドポイントにフィルターをマップします。</span><span class="sxs-lookup"><span data-stu-id="1fbb9-110">Maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="1fbb9-111">このフィルターに一致するメッセージは、この宛先に送信されます。</span><span class="sxs-lookup"><span data-stu-id="1fbb9-111">Messages matching this filter will be sent to this destination.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1fbb9-112">親要素</span><span class="sxs-lookup"><span data-stu-id="1fbb9-112">Parent Elements</span></span>  
  
|<span data-ttu-id="1fbb9-113">要素</span><span class="sxs-lookup"><span data-stu-id="1fbb9-113">Element</span></span>|<span data-ttu-id="1fbb9-114">説明</span><span class="sxs-lookup"><span data-stu-id="1fbb9-114">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="1fbb9-115">ルーティング テーブルを含む構成セクション。</span><span class="sxs-lookup"><span data-stu-id="1fbb9-115">A configuration section that contains a routing table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1fbb9-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="1fbb9-116">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
