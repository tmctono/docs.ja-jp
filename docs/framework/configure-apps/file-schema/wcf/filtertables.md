---
title: <filterTables>
ms.date: 03/30/2017
ms.assetid: 41f1ac35-f559-473a-b2c3-8cc83a6a3831
ms.openlocfilehash: faa26ca108010330475725f83dfd0c6668cfc6b1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178204"
---
# \<filterTables>

<span data-ttu-id="33e5c-101">ルーティング フィルターとターゲット エンドポイントとのマッピングを格納するルーティング テーブルを定義する構成セクションを表します。フィルターが一致したときにメッセージを送信するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="33e5c-101">Represents a configuration section for defining routing tables that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filterTables>**  
  
## <a name="syntax"></a><span data-ttu-id="33e5c-102">構文</span><span class="sxs-lookup"><span data-stu-id="33e5c-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="33e5c-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="33e5c-103">Attributes and Elements</span></span>  

 <span data-ttu-id="33e5c-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="33e5c-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="33e5c-105">属性</span><span class="sxs-lookup"><span data-stu-id="33e5c-105">Attributes</span></span>  

 <span data-ttu-id="33e5c-106">なし。</span><span class="sxs-lookup"><span data-stu-id="33e5c-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="33e5c-107">子要素</span><span class="sxs-lookup"><span data-stu-id="33e5c-107">Child Elements</span></span>  
  
|<span data-ttu-id="33e5c-108">要素</span><span class="sxs-lookup"><span data-stu-id="33e5c-108">Element</span></span>|<span data-ttu-id="33e5c-109">説明</span><span class="sxs-lookup"><span data-stu-id="33e5c-109">Description</span></span>|  
|-------------|-----------------|  
|[\<filters>](filters-of-routing.md)|<span data-ttu-id="33e5c-110">ルーティング フィルターとターゲット エンドポイントとのマッピングを格納するルーティング テーブル。フィルターが一致したときにメッセージを送信するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="33e5c-110">A routing table that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="33e5c-111">親要素</span><span class="sxs-lookup"><span data-stu-id="33e5c-111">Parent Elements</span></span>  
  
|<span data-ttu-id="33e5c-112">要素</span><span class="sxs-lookup"><span data-stu-id="33e5c-112">Element</span></span>|<span data-ttu-id="33e5c-113">説明</span><span class="sxs-lookup"><span data-stu-id="33e5c-113">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="33e5c-114">ルーティング フィルターおよびルーティング テーブルを含む構成セクション。</span><span class="sxs-lookup"><span data-stu-id="33e5c-114">A configuration section that contains routing filters and routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="33e5c-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="33e5c-115">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableCollection?displayProperty=nameWithType>
