---
title: <entries>
ms.date: 03/30/2017
ms.assetid: 202e430c-c1b9-4343-abe2-ac78c181a3b7
ms.openlocfilehash: ffe2538fa2c3cb680285cfaa68c975c0f9d4b1bd
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855282"
---
# <a name="entries"></a><span data-ttu-id="a704d-101">\<エントリ ></span><span class="sxs-lookup"><span data-stu-id="a704d-101">\<entries></span></span>
<span data-ttu-id="a704d-102">ルーティング フィルターとターゲット エンドポイントとのマッピングを格納するルーティング エントリ。フィルターが一致したときにメッセージを送信するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="a704d-102">A routing entry that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
<span data-ttu-id="a704d-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a704d-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a704d-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="a704d-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="a704d-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ルーティング >** ](routing.md)</span><span class="sxs-lookup"><span data-stu-id="a704d-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="a704d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<filterTables >** ](filtertables.md)</span><span class="sxs-lookup"><span data-stu-id="a704d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTables>**](filtertables.md)</span></span>\
<span data-ttu-id="a704d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<filterTable >** ](filtertable.md)</span><span class="sxs-lookup"><span data-stu-id="a704d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTable>**](filtertable.md)</span></span>\
<span data-ttu-id="a704d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<エントリ >**</span><span class="sxs-lookup"><span data-stu-id="a704d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<entries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a704d-109">構文</span><span class="sxs-lookup"><span data-stu-id="a704d-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a704d-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a704d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a704d-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a704d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a704d-112">属性</span><span class="sxs-lookup"><span data-stu-id="a704d-112">Attributes</span></span>  
 <span data-ttu-id="a704d-113">なし。</span><span class="sxs-lookup"><span data-stu-id="a704d-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a704d-114">子要素</span><span class="sxs-lookup"><span data-stu-id="a704d-114">Child Elements</span></span>  
  
|<span data-ttu-id="a704d-115">要素</span><span class="sxs-lookup"><span data-stu-id="a704d-115">Element</span></span>|<span data-ttu-id="a704d-116">説明</span><span class="sxs-lookup"><span data-stu-id="a704d-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a704d-117">\<filters></span><span class="sxs-lookup"><span data-stu-id="a704d-117">\<filters></span></span>](filters-of-routing.md)|<span data-ttu-id="a704d-118">以前に定義されたクライアント エンドポイントにフィルターをマップします。</span><span class="sxs-lookup"><span data-stu-id="a704d-118">Maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="a704d-119">このフィルターに一致するメッセージは、この宛先に送信されます。</span><span class="sxs-lookup"><span data-stu-id="a704d-119">Messages matching this filter will be sent to this destination.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a704d-120">親要素</span><span class="sxs-lookup"><span data-stu-id="a704d-120">Parent Elements</span></span>  
  
|<span data-ttu-id="a704d-121">要素</span><span class="sxs-lookup"><span data-stu-id="a704d-121">Element</span></span>|<span data-ttu-id="a704d-122">説明</span><span class="sxs-lookup"><span data-stu-id="a704d-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a704d-123">\<ルーティング ></span><span class="sxs-lookup"><span data-stu-id="a704d-123">\<routing></span></span>](routing.md)|<span data-ttu-id="a704d-124">ルーティング テーブルを含む構成セクション。</span><span class="sxs-lookup"><span data-stu-id="a704d-124">A configuration section that contains a routing table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a704d-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="a704d-125">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
