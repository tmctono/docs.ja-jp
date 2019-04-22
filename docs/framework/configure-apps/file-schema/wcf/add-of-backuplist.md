---
title: <add> の <backupList>
ms.date: 03/30/2017
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
ms.openlocfilehash: 03bf1bbb8156e4722d987e171d9034747ac6bb61
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59089537"
---
# <a name="add-of-backuplist"></a><span data-ttu-id="33cea-102">\<add> of \<backupList></span><span class="sxs-lookup"><span data-stu-id="33cea-102">\<add> of \<backupList></span></span>
<span data-ttu-id="33cea-103">バックアップ エンドポイント要素を定義する構成要素を表します。</span><span class="sxs-lookup"><span data-stu-id="33cea-103">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
 <span data-ttu-id="33cea-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="33cea-104">\<system.serviceModel></span></span>  
<span data-ttu-id="33cea-105">\<ルーティング ></span><span class="sxs-lookup"><span data-stu-id="33cea-105">\<routing></span></span>  
<span data-ttu-id="33cea-106">\<backupLists ></span><span class="sxs-lookup"><span data-stu-id="33cea-106">\<backupLists></span></span>  
<span data-ttu-id="33cea-107">\<backupList></span><span class="sxs-lookup"><span data-stu-id="33cea-107">\<backupList></span></span>  
<span data-ttu-id="33cea-108">\<add></span><span class="sxs-lookup"><span data-stu-id="33cea-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33cea-109">構文</span><span class="sxs-lookup"><span data-stu-id="33cea-109">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="33cea-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="33cea-110">Attributes and Elements</span></span>  
 <span data-ttu-id="33cea-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="33cea-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="33cea-112">属性</span><span class="sxs-lookup"><span data-stu-id="33cea-112">Attributes</span></span>  
  
|<span data-ttu-id="33cea-113">属性</span><span class="sxs-lookup"><span data-stu-id="33cea-113">Attribute</span></span>|<span data-ttu-id="33cea-114">説明</span><span class="sxs-lookup"><span data-stu-id="33cea-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="33cea-115">name</span><span class="sxs-lookup"><span data-stu-id="33cea-115">name</span></span>|<span data-ttu-id="33cea-116">バックアップ エンドポイントの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="33cea-116">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="33cea-117">子要素</span><span class="sxs-lookup"><span data-stu-id="33cea-117">Child Elements</span></span>  
 <span data-ttu-id="33cea-118">なし。</span><span class="sxs-lookup"><span data-stu-id="33cea-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="33cea-119">親要素</span><span class="sxs-lookup"><span data-stu-id="33cea-119">Parent Elements</span></span>  
  
|<span data-ttu-id="33cea-120">要素</span><span class="sxs-lookup"><span data-stu-id="33cea-120">Element</span></span>|<span data-ttu-id="33cea-121">説明</span><span class="sxs-lookup"><span data-stu-id="33cea-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="33cea-122">\<ルーティング ></span><span class="sxs-lookup"><span data-stu-id="33cea-122">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="33cea-123">プライマリ エンドポイントに接続できない場合に使用するルーティング サービスが希望されるエンドポイントの一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="33cea-123">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="33cea-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="33cea-124">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType>
