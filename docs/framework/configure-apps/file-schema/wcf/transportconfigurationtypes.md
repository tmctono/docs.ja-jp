---
title: <transportConfigurationTypes>
ms.date: 03/30/2017
ms.assetid: 929c8b0a-5460-4f66-a098-2cb8d4e10b69
ms.openlocfilehash: bfd2147a8e772848fc98cab7a875a51bdb53b5cc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941157"
---
# <a name="transportconfigurationtypes"></a><span data-ttu-id="8cf2d-101">\<transportConfigurationTypes ></span><span class="sxs-lookup"><span data-stu-id="8cf2d-101">\<transportConfigurationTypes></span></span>
<span data-ttu-id="8cf2d-102">特定のトランスポートの型を識別する構成要素のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="8cf2d-102">Represents a collection of configuration elements that identify the type of a particular transport.</span></span> <span data-ttu-id="8cf2d-103">これはカスタム WAS プロトコルの追加に使用できます。</span><span class="sxs-lookup"><span data-stu-id="8cf2d-103">This can be used to add custom WAS protocols.</span></span>  
  
 <span data-ttu-id="8cf2d-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="8cf2d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="8cf2d-105">\<ServiceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="8cf2d-105">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="8cf2d-106">\<transportConfigurationTypes ></span><span class="sxs-lookup"><span data-stu-id="8cf2d-106">\<transportConfigurationTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8cf2d-107">構文</span><span class="sxs-lookup"><span data-stu-id="8cf2d-107">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8cf2d-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="8cf2d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="8cf2d-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="8cf2d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8cf2d-110">属性</span><span class="sxs-lookup"><span data-stu-id="8cf2d-110">Attributes</span></span>  
  
|<span data-ttu-id="8cf2d-111">属性</span><span class="sxs-lookup"><span data-stu-id="8cf2d-111">Attribute</span></span>|<span data-ttu-id="8cf2d-112">説明</span><span class="sxs-lookup"><span data-stu-id="8cf2d-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8cf2d-113">name</span><span class="sxs-lookup"><span data-stu-id="8cf2d-113">name</span></span>|<span data-ttu-id="8cf2d-114">トランスポートの名前</span><span class="sxs-lookup"><span data-stu-id="8cf2d-114">The name of the transport</span></span>|  
|<span data-ttu-id="8cf2d-115">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="8cf2d-115">transportConfigurationType</span></span>|<span data-ttu-id="8cf2d-116">トランスポートを実装する型</span><span class="sxs-lookup"><span data-stu-id="8cf2d-116">The type that implements the transport</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8cf2d-117">子要素</span><span class="sxs-lookup"><span data-stu-id="8cf2d-117">Child Elements</span></span>  
  
|<span data-ttu-id="8cf2d-118">要素</span><span class="sxs-lookup"><span data-stu-id="8cf2d-118">Element</span></span>|<span data-ttu-id="8cf2d-119">説明</span><span class="sxs-lookup"><span data-stu-id="8cf2d-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8cf2d-120">\<add></span><span class="sxs-lookup"><span data-stu-id="8cf2d-120">\<add></span></span>](add-of-transportconfigurationtype.md)|<span data-ttu-id="8cf2d-121">特定のトランスポートの型を識別する構成要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="8cf2d-121">Adds a configuration element that identifies the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8cf2d-122">親要素</span><span class="sxs-lookup"><span data-stu-id="8cf2d-122">Parent Elements</span></span>  
  
|<span data-ttu-id="8cf2d-123">要素</span><span class="sxs-lookup"><span data-stu-id="8cf2d-123">Element</span></span>|<span data-ttu-id="8cf2d-124">説明</span><span class="sxs-lookup"><span data-stu-id="8cf2d-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8cf2d-125">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="8cf2d-125">\<serviceHostingEnvironment></span></span>](servicehostingenvironment.md)|<span data-ttu-id="8cf2d-126">環境をホストするサービスがインスタンス化する特定のトランスポートの型を定義します。</span><span class="sxs-lookup"><span data-stu-id="8cf2d-126">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8cf2d-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="8cf2d-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElementCollection>
- [<span data-ttu-id="8cf2d-128">ホスティング</span><span class="sxs-lookup"><span data-stu-id="8cf2d-128">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
