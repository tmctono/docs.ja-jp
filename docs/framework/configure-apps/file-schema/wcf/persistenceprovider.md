---
title: <persistenceProvider>
ms.date: 03/30/2017
ms.assetid: a37049c5-a7ea-4519-94f2-912eeb010380
ms.openlocfilehash: dbf0ba565d4e3e2d65b4a81eb5d345fa90fb43c7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181428"
---
# \<persistenceProvider>

<span data-ttu-id="fd86e-101">使用する永続化プロバイダーの実装の型と、永続化操作に使用するタイムアウトを指定します。</span><span class="sxs-lookup"><span data-stu-id="fd86e-101">Specifies the type of the persistence provider implementation to use, as well as the time-out to use for persistence operations.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<persistenceProvider>**  
  
## <a name="syntax"></a><span data-ttu-id="fd86e-102">構文</span><span class="sxs-lookup"><span data-stu-id="fd86e-102">Syntax</span></span>  
  
```xml  
<persistenceProvider persistenceOperationTimeout="TimeSpan"
                     type="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fd86e-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="fd86e-103">Attributes and Elements</span></span>  

 <span data-ttu-id="fd86e-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="fd86e-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fd86e-105">属性</span><span class="sxs-lookup"><span data-stu-id="fd86e-105">Attributes</span></span>  
  
|<span data-ttu-id="fd86e-106">属性</span><span class="sxs-lookup"><span data-stu-id="fd86e-106">Attribute</span></span>|<span data-ttu-id="fd86e-107">[説明]</span><span class="sxs-lookup"><span data-stu-id="fd86e-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fd86e-108">persistenceOperationTimeout</span><span class="sxs-lookup"><span data-stu-id="fd86e-108">persistenceOperationTimeout</span></span>|<span data-ttu-id="fd86e-109">永続化動作に使用するタイムアウトを指定する <xref:System.TimeSpan> 値。</span><span class="sxs-lookup"><span data-stu-id="fd86e-109">A <xref:System.TimeSpan> value that specifies the time-out used for persistence operations.</span></span> <span data-ttu-id="fd86e-110">既定値は "00:00:30" です。</span><span class="sxs-lookup"><span data-stu-id="fd86e-110">The default is "00:00:30".</span></span>|  
|<span data-ttu-id="fd86e-111">type</span><span class="sxs-lookup"><span data-stu-id="fd86e-111">type</span></span>|<span data-ttu-id="fd86e-112">使用する永続化プロバイダー ファクトリの型を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="fd86e-112">A string that specifies the type of the persistence provider factory to use.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fd86e-113">子要素</span><span class="sxs-lookup"><span data-stu-id="fd86e-113">Child Elements</span></span>  

 <span data-ttu-id="fd86e-114">なし。</span><span class="sxs-lookup"><span data-stu-id="fd86e-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fd86e-115">親要素</span><span class="sxs-lookup"><span data-stu-id="fd86e-115">Parent Elements</span></span>  
  
|<span data-ttu-id="fd86e-116">要素</span><span class="sxs-lookup"><span data-stu-id="fd86e-116">Element</span></span>|<span data-ttu-id="fd86e-117">説明</span><span class="sxs-lookup"><span data-stu-id="fd86e-117">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="fd86e-118">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="fd86e-118">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd86e-119">解説</span><span class="sxs-lookup"><span data-stu-id="fd86e-119">Remarks</span></span>  

 <span data-ttu-id="fd86e-120">この要素は、WCF サービスの状態をシリアル化するために使用される永続化プロバイダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="fd86e-120">This element specifies the persistence provider to be used to serialize the state of a WCF service.</span></span> <span data-ttu-id="fd86e-121">HTTP ヘッダーに状態情報を渡す `wsHttpContextBinding` と一緒に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd86e-121">It should be used together with the `wsHttpContextBinding` which passes state information in HTTP headers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd86e-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="fd86e-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.PersistenceProviderElement>
- <xref:System.ServiceModel.Persistence.PersistenceProvider>
