---
title: <transportConfigurationTypes>
ms.date: 03/30/2017
ms.assetid: 929c8b0a-5460-4f66-a098-2cb8d4e10b69
ms.openlocfilehash: b3683a198ec403fb9966bb902c936108fd043bfa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59083648"
---
# <a name="transportconfigurationtypes"></a><span data-ttu-id="18650-101">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="18650-101">\<transportConfigurationTypes></span></span>
<span data-ttu-id="18650-102">特定のトランスポートの型を識別する構成要素のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="18650-102">Represents a collection of configuration elements that identify the type of a particular transport.</span></span> <span data-ttu-id="18650-103">これはカスタム WAS プロトコルの追加に使用できます。</span><span class="sxs-lookup"><span data-stu-id="18650-103">This can be used to add custom WAS protocols.</span></span>  
  
 <span data-ttu-id="18650-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="18650-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="18650-105">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="18650-105">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="18650-106">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="18650-106">\<transportConfigurationTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18650-107">構文</span><span class="sxs-lookup"><span data-stu-id="18650-107">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="18650-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="18650-108">Attributes and Elements</span></span>  
 <span data-ttu-id="18650-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="18650-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="18650-110">属性</span><span class="sxs-lookup"><span data-stu-id="18650-110">Attributes</span></span>  
  
|<span data-ttu-id="18650-111">属性</span><span class="sxs-lookup"><span data-stu-id="18650-111">Attribute</span></span>|<span data-ttu-id="18650-112">説明</span><span class="sxs-lookup"><span data-stu-id="18650-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="18650-113">name</span><span class="sxs-lookup"><span data-stu-id="18650-113">name</span></span>|<span data-ttu-id="18650-114">トランスポートの名前</span><span class="sxs-lookup"><span data-stu-id="18650-114">The name of the transport</span></span>|  
|<span data-ttu-id="18650-115">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="18650-115">transportConfigurationType</span></span>|<span data-ttu-id="18650-116">トランスポートを実装する型</span><span class="sxs-lookup"><span data-stu-id="18650-116">The type that implements the transport</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="18650-117">子要素</span><span class="sxs-lookup"><span data-stu-id="18650-117">Child Elements</span></span>  
  
|<span data-ttu-id="18650-118">要素</span><span class="sxs-lookup"><span data-stu-id="18650-118">Element</span></span>|<span data-ttu-id="18650-119">説明</span><span class="sxs-lookup"><span data-stu-id="18650-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="18650-120">\<add></span><span class="sxs-lookup"><span data-stu-id="18650-120">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-transportconfigurationtype.md)|<span data-ttu-id="18650-121">特定のトランスポートの型を識別する構成要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="18650-121">Adds a configuration element that identifies the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="18650-122">親要素</span><span class="sxs-lookup"><span data-stu-id="18650-122">Parent Elements</span></span>  
  
|<span data-ttu-id="18650-123">要素</span><span class="sxs-lookup"><span data-stu-id="18650-123">Element</span></span>|<span data-ttu-id="18650-124">説明</span><span class="sxs-lookup"><span data-stu-id="18650-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="18650-125">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="18650-125">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="18650-126">環境をホストするサービスがインスタンス化する特定のトランスポートの型を定義します。</span><span class="sxs-lookup"><span data-stu-id="18650-126">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="18650-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="18650-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElementCollection>
- [<span data-ttu-id="18650-128">ホスト</span><span class="sxs-lookup"><span data-stu-id="18650-128">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
