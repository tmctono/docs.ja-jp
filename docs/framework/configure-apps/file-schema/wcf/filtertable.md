---
title: <filterTable>
ms.date: 03/30/2017
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
ms.openlocfilehash: 918a365004efea82f4ef4c8868f6821d4bb6da18
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855193"
---
# \<filterTable>
<span data-ttu-id="c97e9-101">メッセージを評価するフィルターの一覧と、フィルターが true に評価された場合にメッセージをルーティングするクライアント エンドポイントを格納するルーティング テーブルを表します。</span><span class="sxs-lookup"><span data-stu-id="c97e9-101">Represents a routing table that contains a list of filters to evaluate messages against and the client endpoint to route messages to if the filter evaluates to true.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTables>**](filtertables.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filterTable>**  
  
## <a name="syntax"></a><span data-ttu-id="c97e9-102">構文</span><span class="sxs-lookup"><span data-stu-id="c97e9-102">Syntax</span></span>  
  
```xml  
<routing>
  <filterTables>
     name="String">
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c97e9-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c97e9-103">Attributes and Elements</span></span>  
 <span data-ttu-id="c97e9-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c97e9-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c97e9-105">属性</span><span class="sxs-lookup"><span data-stu-id="c97e9-105">Attributes</span></span>  
  
|<span data-ttu-id="c97e9-106">要素</span><span class="sxs-lookup"><span data-stu-id="c97e9-106">Element</span></span>|<span data-ttu-id="c97e9-107">説明</span><span class="sxs-lookup"><span data-stu-id="c97e9-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c97e9-108">name</span><span class="sxs-lookup"><span data-stu-id="c97e9-108">name</span></span>|<span data-ttu-id="c97e9-109">この構成要素の一意の名前を示す文字列。</span><span class="sxs-lookup"><span data-stu-id="c97e9-109">A string that contains the unique name of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c97e9-110">子要素</span><span class="sxs-lookup"><span data-stu-id="c97e9-110">Child Elements</span></span>  
  
|<span data-ttu-id="c97e9-111">要素</span><span class="sxs-lookup"><span data-stu-id="c97e9-111">Element</span></span>|<span data-ttu-id="c97e9-112">説明</span><span class="sxs-lookup"><span data-stu-id="c97e9-112">Description</span></span>|  
|-------------|-----------------|  
|[\<filters>](filters-of-routing.md)|<span data-ttu-id="c97e9-113">ルーティング フィルターとターゲット エンドポイントとのマッピング。フィルターが一致したときにメッセージを送信するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c97e9-113">Mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c97e9-114">親要素</span><span class="sxs-lookup"><span data-stu-id="c97e9-114">Parent Elements</span></span>  
  
|<span data-ttu-id="c97e9-115">要素</span><span class="sxs-lookup"><span data-stu-id="c97e9-115">Element</span></span>|<span data-ttu-id="c97e9-116">説明</span><span class="sxs-lookup"><span data-stu-id="c97e9-116">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="c97e9-117">ルーティング テーブルを含む構成セクション。</span><span class="sxs-lookup"><span data-stu-id="c97e9-117">A configuration section that contains routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c97e9-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="c97e9-118">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
