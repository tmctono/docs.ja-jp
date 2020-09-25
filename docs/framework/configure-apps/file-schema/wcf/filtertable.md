---
title: <filterTable>
ms.date: 03/30/2017
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
ms.openlocfilehash: fb36feedc5fb2cbdf3827cbe44242c7ac6ab8a9b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185692"
---
# \<filterTable>

<span data-ttu-id="328b8-101">メッセージを評価するフィルターの一覧と、フィルターが true に評価された場合にメッセージをルーティングするクライアント エンドポイントを格納するルーティング テーブルを表します。</span><span class="sxs-lookup"><span data-stu-id="328b8-101">Represents a routing table that contains a list of filters to evaluate messages against and the client endpoint to route messages to if the filter evaluates to true.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTables>**](filtertables.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filterTable>**  
  
## <a name="syntax"></a><span data-ttu-id="328b8-102">構文</span><span class="sxs-lookup"><span data-stu-id="328b8-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="328b8-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="328b8-103">Attributes and Elements</span></span>  

 <span data-ttu-id="328b8-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="328b8-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="328b8-105">属性</span><span class="sxs-lookup"><span data-stu-id="328b8-105">Attributes</span></span>  
  
|<span data-ttu-id="328b8-106">要素</span><span class="sxs-lookup"><span data-stu-id="328b8-106">Element</span></span>|<span data-ttu-id="328b8-107">説明</span><span class="sxs-lookup"><span data-stu-id="328b8-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="328b8-108">name</span><span class="sxs-lookup"><span data-stu-id="328b8-108">name</span></span>|<span data-ttu-id="328b8-109">この構成要素の一意の名前を示す文字列。</span><span class="sxs-lookup"><span data-stu-id="328b8-109">A string that contains the unique name of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="328b8-110">子要素</span><span class="sxs-lookup"><span data-stu-id="328b8-110">Child Elements</span></span>  
  
|<span data-ttu-id="328b8-111">要素</span><span class="sxs-lookup"><span data-stu-id="328b8-111">Element</span></span>|<span data-ttu-id="328b8-112">説明</span><span class="sxs-lookup"><span data-stu-id="328b8-112">Description</span></span>|  
|-------------|-----------------|  
|[\<filters>](filters-of-routing.md)|<span data-ttu-id="328b8-113">ルーティング フィルターとターゲット エンドポイントとのマッピング。フィルターが一致したときにメッセージを送信するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="328b8-113">Mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="328b8-114">親要素</span><span class="sxs-lookup"><span data-stu-id="328b8-114">Parent Elements</span></span>  
  
|<span data-ttu-id="328b8-115">要素</span><span class="sxs-lookup"><span data-stu-id="328b8-115">Element</span></span>|<span data-ttu-id="328b8-116">説明</span><span class="sxs-lookup"><span data-stu-id="328b8-116">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="328b8-117">ルーティング テーブルを含む構成セクション。</span><span class="sxs-lookup"><span data-stu-id="328b8-117">A configuration section that contains routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="328b8-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="328b8-118">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
