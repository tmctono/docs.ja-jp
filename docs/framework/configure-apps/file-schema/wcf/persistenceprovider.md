---
title: <persistenceProvider>
ms.date: 03/30/2017
ms.assetid: a37049c5-a7ea-4519-94f2-912eeb010380
ms.openlocfilehash: dc8dea0ddd1ea074c08952e3e2ebfef2d12f7183
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59099288"
---
# <a name="persistenceprovider"></a><span data-ttu-id="024aa-101">\<persistenceProvider ></span><span class="sxs-lookup"><span data-stu-id="024aa-101">\<persistenceProvider></span></span>
<span data-ttu-id="024aa-102">使用する永続化プロバイダーの実装の型と、永続化操作に使用するタイムアウトを指定します。</span><span class="sxs-lookup"><span data-stu-id="024aa-102">Specifies the type of the persistence provider implementation to use, as well as the time-out to use for persistence operations.</span></span>  
  
 <span data-ttu-id="024aa-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="024aa-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="024aa-104">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="024aa-104">\<behaviors></span></span>  
<span data-ttu-id="024aa-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="024aa-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="024aa-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="024aa-106">\<behavior></span></span>  
<span data-ttu-id="024aa-107">\<persistenceProvider ></span><span class="sxs-lookup"><span data-stu-id="024aa-107">\<persistenceProvider></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="024aa-108">構文</span><span class="sxs-lookup"><span data-stu-id="024aa-108">Syntax</span></span>  
  
```xml  
<persistenceProvider persistenceOperationTimeout="TimeSpan"
                     type="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="024aa-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="024aa-109">Attributes and Elements</span></span>  
 <span data-ttu-id="024aa-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="024aa-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="024aa-111">属性</span><span class="sxs-lookup"><span data-stu-id="024aa-111">Attributes</span></span>  
  
|<span data-ttu-id="024aa-112">属性</span><span class="sxs-lookup"><span data-stu-id="024aa-112">Attribute</span></span>|<span data-ttu-id="024aa-113">説明</span><span class="sxs-lookup"><span data-stu-id="024aa-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="024aa-114">persistenceOperationTimeout</span><span class="sxs-lookup"><span data-stu-id="024aa-114">persistenceOperationTimeout</span></span>|<span data-ttu-id="024aa-115">永続化動作に使用するタイムアウトを指定する <xref:System.TimeSpan> 値。</span><span class="sxs-lookup"><span data-stu-id="024aa-115">A <xref:System.TimeSpan> value that specifies the time-out used for persistence operations.</span></span> <span data-ttu-id="024aa-116">既定値は"00: 00:30"。</span><span class="sxs-lookup"><span data-stu-id="024aa-116">The default is "00:00:30".</span></span>|  
|<span data-ttu-id="024aa-117">種類</span><span class="sxs-lookup"><span data-stu-id="024aa-117">type</span></span>|<span data-ttu-id="024aa-118">使用する永続化プロバイダー ファクトリの型を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="024aa-118">A string that specifies the type of the persistence provider factory to use.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="024aa-119">子要素</span><span class="sxs-lookup"><span data-stu-id="024aa-119">Child Elements</span></span>  
 <span data-ttu-id="024aa-120">なし。</span><span class="sxs-lookup"><span data-stu-id="024aa-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="024aa-121">親要素</span><span class="sxs-lookup"><span data-stu-id="024aa-121">Parent Elements</span></span>  
  
|<span data-ttu-id="024aa-122">要素</span><span class="sxs-lookup"><span data-stu-id="024aa-122">Element</span></span>|<span data-ttu-id="024aa-123">説明</span><span class="sxs-lookup"><span data-stu-id="024aa-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="024aa-124">\<behavior></span><span class="sxs-lookup"><span data-stu-id="024aa-124">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="024aa-125">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="024aa-125">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="024aa-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="024aa-126">Remarks</span></span>  
 <span data-ttu-id="024aa-127">この要素は、WCF サービスの状態をシリアル化するために使用される永続化プロバイダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="024aa-127">This element specifies the persistence provider to be used to serialize the state of a WCF service.</span></span> <span data-ttu-id="024aa-128">HTTP ヘッダーに状態情報を渡す `wsHttpContextBinding` と一緒に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="024aa-128">It should be used together with the `wsHttpContextBinding` which passes state information in HTTP headers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="024aa-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="024aa-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.PersistenceProviderElement>
- <xref:System.ServiceModel.Persistence.PersistenceProvider>
