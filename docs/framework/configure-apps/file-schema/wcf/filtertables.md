---
title: <filterTables>
ms.date: 03/30/2017
ms.assetid: 41f1ac35-f559-473a-b2c3-8cc83a6a3831
ms.openlocfilehash: c68479737cefe542a10a404a8b31a4820a430ffb
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855206"
---
# <a name="filtertables"></a><span data-ttu-id="ea103-101">\<filterTables ></span><span class="sxs-lookup"><span data-stu-id="ea103-101">\<filterTables></span></span>
<span data-ttu-id="ea103-102">ルーティング フィルターとターゲット エンドポイントとのマッピングを格納するルーティング テーブルを定義する構成セクションを表します。フィルターが一致したときにメッセージを送信するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="ea103-102">Represents a configuration section for defining routing tables that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
<span data-ttu-id="ea103-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ea103-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ea103-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="ea103-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="ea103-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ルーティング >** ](routing.md)</span><span class="sxs-lookup"><span data-stu-id="ea103-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="ea103-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<filterTables >**</span><span class="sxs-lookup"><span data-stu-id="ea103-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filterTables>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea103-107">構文</span><span class="sxs-lookup"><span data-stu-id="ea103-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ea103-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ea103-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ea103-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ea103-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ea103-110">属性</span><span class="sxs-lookup"><span data-stu-id="ea103-110">Attributes</span></span>  
 <span data-ttu-id="ea103-111">なし。</span><span class="sxs-lookup"><span data-stu-id="ea103-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ea103-112">子要素</span><span class="sxs-lookup"><span data-stu-id="ea103-112">Child Elements</span></span>  
  
|<span data-ttu-id="ea103-113">要素</span><span class="sxs-lookup"><span data-stu-id="ea103-113">Element</span></span>|<span data-ttu-id="ea103-114">説明</span><span class="sxs-lookup"><span data-stu-id="ea103-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ea103-115">\<filters></span><span class="sxs-lookup"><span data-stu-id="ea103-115">\<filters></span></span>](filters-of-routing.md)|<span data-ttu-id="ea103-116">ルーティング フィルターとターゲット エンドポイントとのマッピングを格納するルーティング テーブル。フィルターが一致したときにメッセージを送信するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="ea103-116">A routing table that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ea103-117">親要素</span><span class="sxs-lookup"><span data-stu-id="ea103-117">Parent Elements</span></span>  
  
|<span data-ttu-id="ea103-118">要素</span><span class="sxs-lookup"><span data-stu-id="ea103-118">Element</span></span>|<span data-ttu-id="ea103-119">説明</span><span class="sxs-lookup"><span data-stu-id="ea103-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ea103-120">\<ルーティング ></span><span class="sxs-lookup"><span data-stu-id="ea103-120">\<routing></span></span>](routing.md)|<span data-ttu-id="ea103-121">ルーティング フィルターおよびルーティング テーブルを含む構成セクション。</span><span class="sxs-lookup"><span data-stu-id="ea103-121">A configuration section that contains routing filters and routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ea103-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="ea103-122">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableCollection?displayProperty=nameWithType>
