---
title: <transportConfigurationTypes>
ms.date: 03/30/2017
ms.assetid: 929c8b0a-5460-4f66-a098-2cb8d4e10b69
ms.openlocfilehash: 4be08f780c1095b0016bd130b5719a2a7307d019
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854927"
---
# \<transportConfigurationTypes>
<span data-ttu-id="8938d-101">特定のトランスポートの型を識別する構成要素のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="8938d-101">Represents a collection of configuration elements that identify the type of a particular transport.</span></span> <span data-ttu-id="8938d-102">これはカスタム WAS プロトコルの追加に使用できます。</span><span class="sxs-lookup"><span data-stu-id="8938d-102">This can be used to add custom WAS protocols.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transportConfigurationTypes>**  
  
## <a name="syntax"></a><span data-ttu-id="8938d-103">構文</span><span class="sxs-lookup"><span data-stu-id="8938d-103">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8938d-104">属性および要素</span><span class="sxs-lookup"><span data-stu-id="8938d-104">Attributes and Elements</span></span>  
 <span data-ttu-id="8938d-105">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="8938d-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8938d-106">属性</span><span class="sxs-lookup"><span data-stu-id="8938d-106">Attributes</span></span>  
  
|<span data-ttu-id="8938d-107">属性</span><span class="sxs-lookup"><span data-stu-id="8938d-107">Attribute</span></span>|<span data-ttu-id="8938d-108">説明</span><span class="sxs-lookup"><span data-stu-id="8938d-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8938d-109">name</span><span class="sxs-lookup"><span data-stu-id="8938d-109">name</span></span>|<span data-ttu-id="8938d-110">トランスポートの名前</span><span class="sxs-lookup"><span data-stu-id="8938d-110">The name of the transport</span></span>|  
|<span data-ttu-id="8938d-111">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="8938d-111">transportConfigurationType</span></span>|<span data-ttu-id="8938d-112">トランスポートを実装する型</span><span class="sxs-lookup"><span data-stu-id="8938d-112">The type that implements the transport</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8938d-113">子要素</span><span class="sxs-lookup"><span data-stu-id="8938d-113">Child Elements</span></span>  
  
|<span data-ttu-id="8938d-114">要素</span><span class="sxs-lookup"><span data-stu-id="8938d-114">Element</span></span>|<span data-ttu-id="8938d-115">Description</span><span class="sxs-lookup"><span data-stu-id="8938d-115">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-transportconfigurationtype.md)|<span data-ttu-id="8938d-116">特定のトランスポートの型を識別する構成要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="8938d-116">Adds a configuration element that identifies the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8938d-117">親要素</span><span class="sxs-lookup"><span data-stu-id="8938d-117">Parent Elements</span></span>  
  
|<span data-ttu-id="8938d-118">要素</span><span class="sxs-lookup"><span data-stu-id="8938d-118">Element</span></span>|<span data-ttu-id="8938d-119">Description</span><span class="sxs-lookup"><span data-stu-id="8938d-119">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceHostingEnvironment>](servicehostingenvironment.md)|<span data-ttu-id="8938d-120">環境をホストするサービスがインスタンス化する特定のトランスポートの型を定義します。</span><span class="sxs-lookup"><span data-stu-id="8938d-120">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8938d-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="8938d-121">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElementCollection>
- [<span data-ttu-id="8938d-122">ホスティング</span><span class="sxs-lookup"><span data-stu-id="8938d-122">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
