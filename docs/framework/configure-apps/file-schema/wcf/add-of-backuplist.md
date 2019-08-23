---
title: <add> の <backupList>
ms.date: 03/30/2017
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
ms.openlocfilehash: c590dbd671807b32e08ad5d871d376a0dc51e611
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926877"
---
# <a name="add-of-backuplist"></a><span data-ttu-id="1bf7f-102">\<backupList > の\<> の追加</span><span class="sxs-lookup"><span data-stu-id="1bf7f-102">\<add> of \<backupList></span></span>
<span data-ttu-id="1bf7f-103">バックアップ エンドポイント要素を定義する構成要素を表します。</span><span class="sxs-lookup"><span data-stu-id="1bf7f-103">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
 <span data-ttu-id="1bf7f-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="1bf7f-104">\<system.serviceModel></span></span>  
<span data-ttu-id="1bf7f-105">\<ルーティング ></span><span class="sxs-lookup"><span data-stu-id="1bf7f-105">\<routing></span></span>  
<span data-ttu-id="1bf7f-106">\<backupLists ></span><span class="sxs-lookup"><span data-stu-id="1bf7f-106">\<backupLists></span></span>  
<span data-ttu-id="1bf7f-107">\<backupList ></span><span class="sxs-lookup"><span data-stu-id="1bf7f-107">\<backupList></span></span>  
<span data-ttu-id="1bf7f-108">\<add></span><span class="sxs-lookup"><span data-stu-id="1bf7f-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bf7f-109">構文</span><span class="sxs-lookup"><span data-stu-id="1bf7f-109">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1bf7f-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1bf7f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1bf7f-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1bf7f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1bf7f-112">属性</span><span class="sxs-lookup"><span data-stu-id="1bf7f-112">Attributes</span></span>  
  
|<span data-ttu-id="1bf7f-113">属性</span><span class="sxs-lookup"><span data-stu-id="1bf7f-113">Attribute</span></span>|<span data-ttu-id="1bf7f-114">説明</span><span class="sxs-lookup"><span data-stu-id="1bf7f-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1bf7f-115">name</span><span class="sxs-lookup"><span data-stu-id="1bf7f-115">name</span></span>|<span data-ttu-id="1bf7f-116">バックアップ エンドポイントの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="1bf7f-116">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1bf7f-117">子要素</span><span class="sxs-lookup"><span data-stu-id="1bf7f-117">Child Elements</span></span>  
 <span data-ttu-id="1bf7f-118">なし。</span><span class="sxs-lookup"><span data-stu-id="1bf7f-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1bf7f-119">親要素</span><span class="sxs-lookup"><span data-stu-id="1bf7f-119">Parent Elements</span></span>  
  
|<span data-ttu-id="1bf7f-120">要素</span><span class="sxs-lookup"><span data-stu-id="1bf7f-120">Element</span></span>|<span data-ttu-id="1bf7f-121">説明</span><span class="sxs-lookup"><span data-stu-id="1bf7f-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1bf7f-122">\<ルーティング ></span><span class="sxs-lookup"><span data-stu-id="1bf7f-122">\<routing></span></span>](routing.md)|<span data-ttu-id="1bf7f-123">プライマリエンドポイントに到達できない場合に、ルーティングサービスで使用するエンドポイントの一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1bf7f-123">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1bf7f-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="1bf7f-124">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType>
