---
title: <transportConfigurationTypes>
ms.date: 03/30/2017
ms.assetid: 929c8b0a-5460-4f66-a098-2cb8d4e10b69
ms.openlocfilehash: b3683a198ec403fb9966bb902c936108fd043bfa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788246"
---
# <a name="transportconfigurationtypes"></a><span data-ttu-id="a9d3f-101">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="a9d3f-101">\<transportConfigurationTypes></span></span>
<span data-ttu-id="a9d3f-102">特定のトランスポートの型を識別する構成要素のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="a9d3f-102">Represents a collection of configuration elements that identify the type of a particular transport.</span></span> <span data-ttu-id="a9d3f-103">これはカスタム WAS プロトコルの追加に使用できます。</span><span class="sxs-lookup"><span data-stu-id="a9d3f-103">This can be used to add custom WAS protocols.</span></span>  
  
 <span data-ttu-id="a9d3f-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="a9d3f-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="a9d3f-105">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="a9d3f-105">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="a9d3f-106">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="a9d3f-106">\<transportConfigurationTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9d3f-107">構文</span><span class="sxs-lookup"><span data-stu-id="a9d3f-107">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a9d3f-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a9d3f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a9d3f-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a9d3f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a9d3f-110">属性</span><span class="sxs-lookup"><span data-stu-id="a9d3f-110">Attributes</span></span>  
  
|<span data-ttu-id="a9d3f-111">属性</span><span class="sxs-lookup"><span data-stu-id="a9d3f-111">Attribute</span></span>|<span data-ttu-id="a9d3f-112">説明</span><span class="sxs-lookup"><span data-stu-id="a9d3f-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a9d3f-113">name</span><span class="sxs-lookup"><span data-stu-id="a9d3f-113">name</span></span>|<span data-ttu-id="a9d3f-114">トランスポートの名前</span><span class="sxs-lookup"><span data-stu-id="a9d3f-114">The name of the transport</span></span>|  
|<span data-ttu-id="a9d3f-115">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="a9d3f-115">transportConfigurationType</span></span>|<span data-ttu-id="a9d3f-116">トランスポートを実装する型</span><span class="sxs-lookup"><span data-stu-id="a9d3f-116">The type that implements the transport</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a9d3f-117">子要素</span><span class="sxs-lookup"><span data-stu-id="a9d3f-117">Child Elements</span></span>  
  
|<span data-ttu-id="a9d3f-118">要素</span><span class="sxs-lookup"><span data-stu-id="a9d3f-118">Element</span></span>|<span data-ttu-id="a9d3f-119">説明</span><span class="sxs-lookup"><span data-stu-id="a9d3f-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a9d3f-120">\<add></span><span class="sxs-lookup"><span data-stu-id="a9d3f-120">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-transportconfigurationtype.md)|<span data-ttu-id="a9d3f-121">特定のトランスポートの型を識別する構成要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="a9d3f-121">Adds a configuration element that identifies the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a9d3f-122">親要素</span><span class="sxs-lookup"><span data-stu-id="a9d3f-122">Parent Elements</span></span>  
  
|<span data-ttu-id="a9d3f-123">要素</span><span class="sxs-lookup"><span data-stu-id="a9d3f-123">Element</span></span>|<span data-ttu-id="a9d3f-124">説明</span><span class="sxs-lookup"><span data-stu-id="a9d3f-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a9d3f-125">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="a9d3f-125">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="a9d3f-126">環境をホストするサービスがインスタンス化する特定のトランスポートの型を定義します。</span><span class="sxs-lookup"><span data-stu-id="a9d3f-126">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a9d3f-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="a9d3f-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElementCollection>
- [<span data-ttu-id="a9d3f-128">ホスティング</span><span class="sxs-lookup"><span data-stu-id="a9d3f-128">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
