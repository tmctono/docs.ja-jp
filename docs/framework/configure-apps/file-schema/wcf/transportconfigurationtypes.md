---
title: <transportConfigurationTypes>
ms.date: 03/30/2017
ms.assetid: 929c8b0a-5460-4f66-a098-2cb8d4e10b69
ms.openlocfilehash: 6545e1f1be2695d165b89a38c7218e0acdc88bfc
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91162024"
---
# \<transportConfigurationTypes>

<span data-ttu-id="f66f7-101">特定のトランスポートの型を識別する構成要素のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="f66f7-101">Represents a collection of configuration elements that identify the type of a particular transport.</span></span> <span data-ttu-id="f66f7-102">これはカスタム WAS プロトコルの追加に使用できます。</span><span class="sxs-lookup"><span data-stu-id="f66f7-102">This can be used to add custom WAS protocols.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transportConfigurationTypes>**  
  
## <a name="syntax"></a><span data-ttu-id="f66f7-103">構文</span><span class="sxs-lookup"><span data-stu-id="f66f7-103">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f66f7-104">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f66f7-104">Attributes and Elements</span></span>  

 <span data-ttu-id="f66f7-105">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f66f7-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f66f7-106">属性</span><span class="sxs-lookup"><span data-stu-id="f66f7-106">Attributes</span></span>  
  
|<span data-ttu-id="f66f7-107">属性</span><span class="sxs-lookup"><span data-stu-id="f66f7-107">Attribute</span></span>|<span data-ttu-id="f66f7-108">説明</span><span class="sxs-lookup"><span data-stu-id="f66f7-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f66f7-109">name</span><span class="sxs-lookup"><span data-stu-id="f66f7-109">name</span></span>|<span data-ttu-id="f66f7-110">トランスポートの名前</span><span class="sxs-lookup"><span data-stu-id="f66f7-110">The name of the transport</span></span>|  
|<span data-ttu-id="f66f7-111">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="f66f7-111">transportConfigurationType</span></span>|<span data-ttu-id="f66f7-112">トランスポートを実装する型</span><span class="sxs-lookup"><span data-stu-id="f66f7-112">The type that implements the transport</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f66f7-113">子要素</span><span class="sxs-lookup"><span data-stu-id="f66f7-113">Child Elements</span></span>  
  
|<span data-ttu-id="f66f7-114">要素</span><span class="sxs-lookup"><span data-stu-id="f66f7-114">Element</span></span>|<span data-ttu-id="f66f7-115">説明</span><span class="sxs-lookup"><span data-stu-id="f66f7-115">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-transportconfigurationtype.md)|<span data-ttu-id="f66f7-116">特定のトランスポートの型を識別する構成要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="f66f7-116">Adds a configuration element that identifies the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f66f7-117">親要素</span><span class="sxs-lookup"><span data-stu-id="f66f7-117">Parent Elements</span></span>  
  
|<span data-ttu-id="f66f7-118">要素</span><span class="sxs-lookup"><span data-stu-id="f66f7-118">Element</span></span>|<span data-ttu-id="f66f7-119">説明</span><span class="sxs-lookup"><span data-stu-id="f66f7-119">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceHostingEnvironment>](servicehostingenvironment.md)|<span data-ttu-id="f66f7-120">環境をホストするサービスがインスタンス化する特定のトランスポートの型を定義します。</span><span class="sxs-lookup"><span data-stu-id="f66f7-120">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f66f7-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="f66f7-121">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElementCollection>
- [<span data-ttu-id="f66f7-122">ホスティング</span><span class="sxs-lookup"><span data-stu-id="f66f7-122">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
