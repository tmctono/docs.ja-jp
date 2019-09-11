---
title: <add> の <backupList>
ms.date: 03/30/2017
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
ms.openlocfilehash: 80726cc22cb56013c85c7704c28579b1337666c9
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850545"
---
# <a name="add-of-backuplist"></a><span data-ttu-id="9feff-102">\<backupList > の\<> の追加</span><span class="sxs-lookup"><span data-stu-id="9feff-102">\<add> of \<backupList></span></span>
<span data-ttu-id="9feff-103">バックアップ エンドポイント要素を定義する構成要素を表します。</span><span class="sxs-lookup"><span data-stu-id="9feff-103">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
<span data-ttu-id="9feff-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9feff-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9feff-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="9feff-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="9feff-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ルーティング >** ](routing.md)</span><span class="sxs-lookup"><span data-stu-id="9feff-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="9feff-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<backupLists >** ](backuplists.md)</span><span class="sxs-lookup"><span data-stu-id="9feff-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<backupLists>**](backuplists.md)</span></span>\
<span data-ttu-id="9feff-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<backupList >** ](backuplist.md)</span><span class="sxs-lookup"><span data-stu-id="9feff-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<backupList>**](backuplist.md)</span></span>\
<span data-ttu-id="9feff-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> の追加**</span><span class="sxs-lookup"><span data-stu-id="9feff-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9feff-110">構文</span><span class="sxs-lookup"><span data-stu-id="9feff-110">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9feff-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="9feff-111">Attributes and Elements</span></span>  
 <span data-ttu-id="9feff-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="9feff-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9feff-113">属性</span><span class="sxs-lookup"><span data-stu-id="9feff-113">Attributes</span></span>  
  
|<span data-ttu-id="9feff-114">属性</span><span class="sxs-lookup"><span data-stu-id="9feff-114">Attribute</span></span>|<span data-ttu-id="9feff-115">説明</span><span class="sxs-lookup"><span data-stu-id="9feff-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9feff-116">name</span><span class="sxs-lookup"><span data-stu-id="9feff-116">name</span></span>|<span data-ttu-id="9feff-117">バックアップ エンドポイントの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="9feff-117">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9feff-118">子要素</span><span class="sxs-lookup"><span data-stu-id="9feff-118">Child Elements</span></span>  
 <span data-ttu-id="9feff-119">なし。</span><span class="sxs-lookup"><span data-stu-id="9feff-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9feff-120">親要素</span><span class="sxs-lookup"><span data-stu-id="9feff-120">Parent Elements</span></span>  
  
|<span data-ttu-id="9feff-121">要素</span><span class="sxs-lookup"><span data-stu-id="9feff-121">Element</span></span>|<span data-ttu-id="9feff-122">説明</span><span class="sxs-lookup"><span data-stu-id="9feff-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9feff-123">\<ルーティング ></span><span class="sxs-lookup"><span data-stu-id="9feff-123">\<routing></span></span>](routing.md)|<span data-ttu-id="9feff-124">プライマリエンドポイントに到達できない場合に、ルーティングサービスで使用するエンドポイントの一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9feff-124">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9feff-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="9feff-125">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType>
