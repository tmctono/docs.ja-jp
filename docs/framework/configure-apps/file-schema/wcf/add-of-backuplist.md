---
title: <add> (行中)  <backupList>
ms.date: 03/30/2017
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
ms.openlocfilehash: 03bf1bbb8156e4722d987e171d9034747ac6bb61
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59089537"
---
# <a name="add-of-backuplist"></a><span data-ttu-id="8491a-102">\<add> of \<backupList></span><span class="sxs-lookup"><span data-stu-id="8491a-102">\<add> of \<backupList></span></span>
<span data-ttu-id="8491a-103">バックアップ エンドポイント要素を定義する構成要素を表します。</span><span class="sxs-lookup"><span data-stu-id="8491a-103">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
 <span data-ttu-id="8491a-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="8491a-104">\<system.serviceModel></span></span>  
<span data-ttu-id="8491a-105">\<ルーティング ></span><span class="sxs-lookup"><span data-stu-id="8491a-105">\<routing></span></span>  
<span data-ttu-id="8491a-106">\<backupLists ></span><span class="sxs-lookup"><span data-stu-id="8491a-106">\<backupLists></span></span>  
<span data-ttu-id="8491a-107">\<backupList></span><span class="sxs-lookup"><span data-stu-id="8491a-107">\<backupList></span></span>  
<span data-ttu-id="8491a-108">\<add></span><span class="sxs-lookup"><span data-stu-id="8491a-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8491a-109">構文</span><span class="sxs-lookup"><span data-stu-id="8491a-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8491a-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="8491a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8491a-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="8491a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8491a-112">属性</span><span class="sxs-lookup"><span data-stu-id="8491a-112">Attributes</span></span>  
  
|<span data-ttu-id="8491a-113">属性</span><span class="sxs-lookup"><span data-stu-id="8491a-113">Attribute</span></span>|<span data-ttu-id="8491a-114">説明</span><span class="sxs-lookup"><span data-stu-id="8491a-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8491a-115">name</span><span class="sxs-lookup"><span data-stu-id="8491a-115">name</span></span>|<span data-ttu-id="8491a-116">バックアップ エンドポイントの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="8491a-116">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8491a-117">子要素</span><span class="sxs-lookup"><span data-stu-id="8491a-117">Child Elements</span></span>  
 <span data-ttu-id="8491a-118">なし。</span><span class="sxs-lookup"><span data-stu-id="8491a-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8491a-119">親要素</span><span class="sxs-lookup"><span data-stu-id="8491a-119">Parent Elements</span></span>  
  
|<span data-ttu-id="8491a-120">要素</span><span class="sxs-lookup"><span data-stu-id="8491a-120">Element</span></span>|<span data-ttu-id="8491a-121">説明</span><span class="sxs-lookup"><span data-stu-id="8491a-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8491a-122">\<ルーティング ></span><span class="sxs-lookup"><span data-stu-id="8491a-122">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="8491a-123">プライマリ エンドポイントに接続できない場合に使用するルーティング サービスが希望されるエンドポイントの一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8491a-123">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8491a-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="8491a-124">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType>
