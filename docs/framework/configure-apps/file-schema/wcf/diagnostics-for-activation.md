---
title: <diagnostics>アクティブ化の場合
ms.date: 03/30/2017
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
ms.openlocfilehash: 33b2cd4c5ae1b4076892a61aa7e2b927efa1ddc1
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400408"
---
# <a name="diagnostics-for-activation"></a><span data-ttu-id="4b804-102">\<アクティブ化のための診断 ></span><span class="sxs-lookup"><span data-stu-id="4b804-102">\<diagnostics> for Activation</span></span>
<span data-ttu-id="4b804-103">Windows Communication Foundation (WCF) リスナーの診断機能を構成します。</span><span class="sxs-lookup"><span data-stu-id="4b804-103">Configures Windows Communication Foundation (WCF) listener's diagnostics functionalities.</span></span>  
  
<span data-ttu-id="4b804-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4b804-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4b804-105">&nbsp;&nbsp;[ **\<System.servicemodel. activation >** ](system-servicemodel-activation.md)</span><span class="sxs-lookup"><span data-stu-id="4b804-105">&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)</span></span>\
<span data-ttu-id="4b804-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<診断 >**</span><span class="sxs-lookup"><span data-stu-id="4b804-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<diagnostics>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b804-107">構文</span><span class="sxs-lookup"><span data-stu-id="4b804-107">Syntax</span></span>  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <diagnostics performanceCountersEnabled="Boolean" />
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a><span data-ttu-id="4b804-108">型</span><span class="sxs-lookup"><span data-stu-id="4b804-108">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4b804-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="4b804-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4b804-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="4b804-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4b804-111">属性</span><span class="sxs-lookup"><span data-stu-id="4b804-111">Attributes</span></span>  
  
|<span data-ttu-id="4b804-112">属性</span><span class="sxs-lookup"><span data-stu-id="4b804-112">Attribute</span></span>|<span data-ttu-id="4b804-113">説明</span><span class="sxs-lookup"><span data-stu-id="4b804-113">Description</span></span>|  
|---------------|-----------------|  
|`performanceCountersEnabled`|<span data-ttu-id="4b804-114">診断用パフォーマンス カウンターが有効であるかどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="4b804-114">A Boolean value that indicates whether performance counters are enabled for diagnostic purposes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4b804-115">子要素</span><span class="sxs-lookup"><span data-stu-id="4b804-115">Child Elements</span></span>  
 <span data-ttu-id="4b804-116">なし。</span><span class="sxs-lookup"><span data-stu-id="4b804-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4b804-117">親要素</span><span class="sxs-lookup"><span data-stu-id="4b804-117">Parent Elements</span></span>  
  
|<span data-ttu-id="4b804-118">要素</span><span class="sxs-lookup"><span data-stu-id="4b804-118">Element</span></span>|<span data-ttu-id="4b804-119">説明</span><span class="sxs-lookup"><span data-stu-id="4b804-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4b804-120">\<system.serviceModel.activation ></span><span class="sxs-lookup"><span data-stu-id="4b804-120">\<system.serviceModel.activation></span></span>](system-servicemodel-activation.md)|<span data-ttu-id="4b804-121">リスナー プロセス SMSvcHost.exe の設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4b804-121">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4b804-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="4b804-122">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>
