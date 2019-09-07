---
title: <persistenceProvider>
ms.date: 03/30/2017
ms.assetid: a37049c5-a7ea-4519-94f2-912eeb010380
ms.openlocfilehash: 7c4d9ae29ca1e543217d444e05a661b48e2cbb62
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400077"
---
# <a name="persistenceprovider"></a><span data-ttu-id="be7fa-101">\<persistenceProvider ></span><span class="sxs-lookup"><span data-stu-id="be7fa-101">\<persistenceProvider></span></span>
<span data-ttu-id="be7fa-102">使用する永続化プロバイダーの実装の型と、永続化操作に使用するタイムアウトを指定します。</span><span class="sxs-lookup"><span data-stu-id="be7fa-102">Specifies the type of the persistence provider implementation to use, as well as the time-out to use for persistence operations.</span></span>  
  
<span data-ttu-id="be7fa-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="be7fa-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="be7fa-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="be7fa-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="be7fa-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="be7fa-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="be7fa-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="be7fa-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="be7fa-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="be7fa-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="be7fa-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<persistenceProvider >**</span><span class="sxs-lookup"><span data-stu-id="be7fa-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<persistenceProvider>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be7fa-109">構文</span><span class="sxs-lookup"><span data-stu-id="be7fa-109">Syntax</span></span>  
  
```xml  
<persistenceProvider persistenceOperationTimeout="TimeSpan"
                     type="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="be7fa-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="be7fa-110">Attributes and Elements</span></span>  
 <span data-ttu-id="be7fa-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="be7fa-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="be7fa-112">属性</span><span class="sxs-lookup"><span data-stu-id="be7fa-112">Attributes</span></span>  
  
|<span data-ttu-id="be7fa-113">属性</span><span class="sxs-lookup"><span data-stu-id="be7fa-113">Attribute</span></span>|<span data-ttu-id="be7fa-114">説明</span><span class="sxs-lookup"><span data-stu-id="be7fa-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="be7fa-115">persistenceOperationTimeout</span><span class="sxs-lookup"><span data-stu-id="be7fa-115">persistenceOperationTimeout</span></span>|<span data-ttu-id="be7fa-116">永続化動作に使用するタイムアウトを指定する <xref:System.TimeSpan> 値。</span><span class="sxs-lookup"><span data-stu-id="be7fa-116">A <xref:System.TimeSpan> value that specifies the time-out used for persistence operations.</span></span> <span data-ttu-id="be7fa-117">既定値は "00:00:30" です。</span><span class="sxs-lookup"><span data-stu-id="be7fa-117">The default is "00:00:30".</span></span>|  
|<span data-ttu-id="be7fa-118">型</span><span class="sxs-lookup"><span data-stu-id="be7fa-118">type</span></span>|<span data-ttu-id="be7fa-119">使用する永続化プロバイダー ファクトリの型を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="be7fa-119">A string that specifies the type of the persistence provider factory to use.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="be7fa-120">子要素</span><span class="sxs-lookup"><span data-stu-id="be7fa-120">Child Elements</span></span>  
 <span data-ttu-id="be7fa-121">なし。</span><span class="sxs-lookup"><span data-stu-id="be7fa-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="be7fa-122">親要素</span><span class="sxs-lookup"><span data-stu-id="be7fa-122">Parent Elements</span></span>  
  
|<span data-ttu-id="be7fa-123">要素</span><span class="sxs-lookup"><span data-stu-id="be7fa-123">Element</span></span>|<span data-ttu-id="be7fa-124">説明</span><span class="sxs-lookup"><span data-stu-id="be7fa-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="be7fa-125">\<behavior></span><span class="sxs-lookup"><span data-stu-id="be7fa-125">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="be7fa-126">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="be7fa-126">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="be7fa-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="be7fa-127">Remarks</span></span>  
 <span data-ttu-id="be7fa-128">この要素は、WCF サービスの状態をシリアル化するために使用される永続化プロバイダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="be7fa-128">This element specifies the persistence provider to be used to serialize the state of a WCF service.</span></span> <span data-ttu-id="be7fa-129">HTTP ヘッダーに状態情報を渡す `wsHttpContextBinding` と一緒に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="be7fa-129">It should be used together with the `wsHttpContextBinding` which passes state information in HTTP headers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be7fa-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="be7fa-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.PersistenceProviderElement>
- <xref:System.ServiceModel.Persistence.PersistenceProvider>
