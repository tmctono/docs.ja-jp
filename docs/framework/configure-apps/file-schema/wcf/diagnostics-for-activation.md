---
title: <diagnostics>アクティブ化の場合
ms.date: 03/30/2017
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
ms.openlocfilehash: 33b2cd4c5ae1b4076892a61aa7e2b927efa1ddc1
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400408"
---
# <a name="diagnostics-for-activation"></a><span data-ttu-id="f58ea-102">\<diagnostics>アクティブ化の場合</span><span class="sxs-lookup"><span data-stu-id="f58ea-102">\<diagnostics> for Activation</span></span>
<span data-ttu-id="f58ea-103">Windows Communication Foundation (WCF) リスナーの診断機能を構成します。</span><span class="sxs-lookup"><span data-stu-id="f58ea-103">Configures Windows Communication Foundation (WCF) listener's diagnostics functionalities.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<diagnostics>**  
  
## <a name="syntax"></a><span data-ttu-id="f58ea-104">構文</span><span class="sxs-lookup"><span data-stu-id="f58ea-104">Syntax</span></span>  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <diagnostics performanceCountersEnabled="Boolean" />
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a><span data-ttu-id="f58ea-105">Type</span><span class="sxs-lookup"><span data-stu-id="f58ea-105">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f58ea-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f58ea-106">Attributes and Elements</span></span>  
 <span data-ttu-id="f58ea-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f58ea-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f58ea-108">属性</span><span class="sxs-lookup"><span data-stu-id="f58ea-108">Attributes</span></span>  
  
|<span data-ttu-id="f58ea-109">属性</span><span class="sxs-lookup"><span data-stu-id="f58ea-109">Attribute</span></span>|<span data-ttu-id="f58ea-110">説明</span><span class="sxs-lookup"><span data-stu-id="f58ea-110">Description</span></span>|  
|---------------|-----------------|  
|`performanceCountersEnabled`|<span data-ttu-id="f58ea-111">診断用パフォーマンス カウンターが有効であるかどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="f58ea-111">A Boolean value that indicates whether performance counters are enabled for diagnostic purposes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f58ea-112">子要素</span><span class="sxs-lookup"><span data-stu-id="f58ea-112">Child Elements</span></span>  
 <span data-ttu-id="f58ea-113">なし。</span><span class="sxs-lookup"><span data-stu-id="f58ea-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f58ea-114">親要素</span><span class="sxs-lookup"><span data-stu-id="f58ea-114">Parent Elements</span></span>  
  
|<span data-ttu-id="f58ea-115">要素</span><span class="sxs-lookup"><span data-stu-id="f58ea-115">Element</span></span>|<span data-ttu-id="f58ea-116">Description</span><span class="sxs-lookup"><span data-stu-id="f58ea-116">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel.activation>](system-servicemodel-activation.md)|<span data-ttu-id="f58ea-117">リスナー プロセス SMSvcHost.exe の設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f58ea-117">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f58ea-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="f58ea-118">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>
