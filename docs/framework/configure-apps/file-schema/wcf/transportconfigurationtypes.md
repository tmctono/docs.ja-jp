---
title: <transportConfigurationTypes>
ms.date: 03/30/2017
ms.assetid: 929c8b0a-5460-4f66-a098-2cb8d4e10b69
ms.openlocfilehash: 4be08f780c1095b0016bd130b5719a2a7307d019
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854927"
---
# <a name="transportconfigurationtypes"></a><span data-ttu-id="4775c-101">\<transportConfigurationTypes ></span><span class="sxs-lookup"><span data-stu-id="4775c-101">\<transportConfigurationTypes></span></span>
<span data-ttu-id="4775c-102">特定のトランスポートの型を識別する構成要素のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="4775c-102">Represents a collection of configuration elements that identify the type of a particular transport.</span></span> <span data-ttu-id="4775c-103">これはカスタム WAS プロトコルの追加に使用できます。</span><span class="sxs-lookup"><span data-stu-id="4775c-103">This can be used to add custom WAS protocols.</span></span>  
  
<span data-ttu-id="4775c-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4775c-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4775c-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="4775c-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="4775c-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceHostingEnvironment >** ](servicehostingenvironment.md)</span><span class="sxs-lookup"><span data-stu-id="4775c-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)</span></span>\
<span data-ttu-id="4775c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<transportConfigurationTypes >**</span><span class="sxs-lookup"><span data-stu-id="4775c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transportConfigurationTypes>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4775c-108">構文</span><span class="sxs-lookup"><span data-stu-id="4775c-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4775c-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="4775c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4775c-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="4775c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4775c-111">属性</span><span class="sxs-lookup"><span data-stu-id="4775c-111">Attributes</span></span>  
  
|<span data-ttu-id="4775c-112">属性</span><span class="sxs-lookup"><span data-stu-id="4775c-112">Attribute</span></span>|<span data-ttu-id="4775c-113">説明</span><span class="sxs-lookup"><span data-stu-id="4775c-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4775c-114">name</span><span class="sxs-lookup"><span data-stu-id="4775c-114">name</span></span>|<span data-ttu-id="4775c-115">トランスポートの名前</span><span class="sxs-lookup"><span data-stu-id="4775c-115">The name of the transport</span></span>|  
|<span data-ttu-id="4775c-116">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="4775c-116">transportConfigurationType</span></span>|<span data-ttu-id="4775c-117">トランスポートを実装する型</span><span class="sxs-lookup"><span data-stu-id="4775c-117">The type that implements the transport</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4775c-118">子要素</span><span class="sxs-lookup"><span data-stu-id="4775c-118">Child Elements</span></span>  
  
|<span data-ttu-id="4775c-119">要素</span><span class="sxs-lookup"><span data-stu-id="4775c-119">Element</span></span>|<span data-ttu-id="4775c-120">説明</span><span class="sxs-lookup"><span data-stu-id="4775c-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4775c-121">\<add></span><span class="sxs-lookup"><span data-stu-id="4775c-121">\<add></span></span>](add-of-transportconfigurationtype.md)|<span data-ttu-id="4775c-122">特定のトランスポートの型を識別する構成要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="4775c-122">Adds a configuration element that identifies the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4775c-123">親要素</span><span class="sxs-lookup"><span data-stu-id="4775c-123">Parent Elements</span></span>  
  
|<span data-ttu-id="4775c-124">要素</span><span class="sxs-lookup"><span data-stu-id="4775c-124">Element</span></span>|<span data-ttu-id="4775c-125">説明</span><span class="sxs-lookup"><span data-stu-id="4775c-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4775c-126">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="4775c-126">\<serviceHostingEnvironment></span></span>](servicehostingenvironment.md)|<span data-ttu-id="4775c-127">環境をホストするサービスがインスタンス化する特定のトランスポートの型を定義します。</span><span class="sxs-lookup"><span data-stu-id="4775c-127">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4775c-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="4775c-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElementCollection>
- [<span data-ttu-id="4775c-129">ホスティング</span><span class="sxs-lookup"><span data-stu-id="4775c-129">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
