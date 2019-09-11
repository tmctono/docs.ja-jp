---
title: <filterTable>
ms.date: 03/30/2017
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
ms.openlocfilehash: 918a365004efea82f4ef4c8868f6821d4bb6da18
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855193"
---
# <a name="filtertable"></a><span data-ttu-id="9174a-101">\<filterTable ></span><span class="sxs-lookup"><span data-stu-id="9174a-101">\<filterTable></span></span>
<span data-ttu-id="9174a-102">メッセージを評価するフィルターの一覧と、フィルターが true と評価された場合にメッセージのルーティング先となるクライアントエンドポイントを含むルーティングテーブルを表します。</span><span class="sxs-lookup"><span data-stu-id="9174a-102">Represents a routing table that contains a list of filters to evaluate messages against and the client endpoint to route messages to if the filter evaluates to true.</span></span>  
  
<span data-ttu-id="9174a-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9174a-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9174a-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="9174a-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="9174a-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ルーティング >** ](routing.md)</span><span class="sxs-lookup"><span data-stu-id="9174a-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="9174a-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<filterTables >** ](filtertables.md)</span><span class="sxs-lookup"><span data-stu-id="9174a-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTables>**](filtertables.md)</span></span>\
<span data-ttu-id="9174a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<filterTable >**</span><span class="sxs-lookup"><span data-stu-id="9174a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filterTable>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9174a-108">構文</span><span class="sxs-lookup"><span data-stu-id="9174a-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9174a-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="9174a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="9174a-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="9174a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9174a-111">属性</span><span class="sxs-lookup"><span data-stu-id="9174a-111">Attributes</span></span>  
  
|<span data-ttu-id="9174a-112">要素</span><span class="sxs-lookup"><span data-stu-id="9174a-112">Element</span></span>|<span data-ttu-id="9174a-113">説明</span><span class="sxs-lookup"><span data-stu-id="9174a-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9174a-114">name</span><span class="sxs-lookup"><span data-stu-id="9174a-114">name</span></span>|<span data-ttu-id="9174a-115">この構成要素の一意の名前を示す文字列。</span><span class="sxs-lookup"><span data-stu-id="9174a-115">A string that contains the unique name of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9174a-116">子要素</span><span class="sxs-lookup"><span data-stu-id="9174a-116">Child Elements</span></span>  
  
|<span data-ttu-id="9174a-117">要素</span><span class="sxs-lookup"><span data-stu-id="9174a-117">Element</span></span>|<span data-ttu-id="9174a-118">説明</span><span class="sxs-lookup"><span data-stu-id="9174a-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9174a-119">\<filters></span><span class="sxs-lookup"><span data-stu-id="9174a-119">\<filters></span></span>](filters-of-routing.md)|<span data-ttu-id="9174a-120">ルーティング フィルターとターゲット エンドポイントとのマッピング。フィルターが一致したときにメッセージを送信するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="9174a-120">Mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9174a-121">親要素</span><span class="sxs-lookup"><span data-stu-id="9174a-121">Parent Elements</span></span>  
  
|<span data-ttu-id="9174a-122">要素</span><span class="sxs-lookup"><span data-stu-id="9174a-122">Element</span></span>|<span data-ttu-id="9174a-123">説明</span><span class="sxs-lookup"><span data-stu-id="9174a-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9174a-124">\<ルーティング ></span><span class="sxs-lookup"><span data-stu-id="9174a-124">\<routing></span></span>](routing.md)|<span data-ttu-id="9174a-125">ルーティング テーブルを含む構成セクション。</span><span class="sxs-lookup"><span data-stu-id="9174a-125">A configuration section that contains routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9174a-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="9174a-126">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
