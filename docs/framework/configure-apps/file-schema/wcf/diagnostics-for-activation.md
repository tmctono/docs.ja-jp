---
title: <diagnostics>アクティブ化の場合
ms.date: 03/30/2017
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
ms.openlocfilehash: 543c41936921eda39017e07f1c97294b268a9141
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919219"
---
# <a name="diagnostics-for-activation"></a><span data-ttu-id="ff202-102">\<アクティブ化のための診断 ></span><span class="sxs-lookup"><span data-stu-id="ff202-102">\<diagnostics> for Activation</span></span>
<span data-ttu-id="ff202-103">Windows Communication Foundation (WCF) リスナーの診断機能を構成します。</span><span class="sxs-lookup"><span data-stu-id="ff202-103">Configures Windows Communication Foundation (WCF) listener's diagnostics functionalities.</span></span>  
  
 <span data-ttu-id="ff202-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="ff202-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="ff202-105">\<診断 ></span><span class="sxs-lookup"><span data-stu-id="ff202-105">\<diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff202-106">構文</span><span class="sxs-lookup"><span data-stu-id="ff202-106">Syntax</span></span>  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <diagnostics performanceCountersEnabled="Boolean" />
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a><span data-ttu-id="ff202-107">型</span><span class="sxs-lookup"><span data-stu-id="ff202-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ff202-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ff202-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ff202-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ff202-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ff202-110">属性</span><span class="sxs-lookup"><span data-stu-id="ff202-110">Attributes</span></span>  
  
|<span data-ttu-id="ff202-111">属性</span><span class="sxs-lookup"><span data-stu-id="ff202-111">Attribute</span></span>|<span data-ttu-id="ff202-112">説明</span><span class="sxs-lookup"><span data-stu-id="ff202-112">Description</span></span>|  
|---------------|-----------------|  
|`performanceCountersEnabled`|<span data-ttu-id="ff202-113">診断用パフォーマンス カウンターが有効であるかどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="ff202-113">A Boolean value that indicates whether performance counters are enabled for diagnostic purposes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ff202-114">子要素</span><span class="sxs-lookup"><span data-stu-id="ff202-114">Child Elements</span></span>  
 <span data-ttu-id="ff202-115">なし。</span><span class="sxs-lookup"><span data-stu-id="ff202-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ff202-116">親要素</span><span class="sxs-lookup"><span data-stu-id="ff202-116">Parent Elements</span></span>  
  
|<span data-ttu-id="ff202-117">要素</span><span class="sxs-lookup"><span data-stu-id="ff202-117">Element</span></span>|<span data-ttu-id="ff202-118">説明</span><span class="sxs-lookup"><span data-stu-id="ff202-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ff202-119">\<system.serviceModel.activation ></span><span class="sxs-lookup"><span data-stu-id="ff202-119">\<system.serviceModel.activation></span></span>](system-servicemodel-activation.md)|<span data-ttu-id="ff202-120">リスナー プロセス SMSvcHost.exe の設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ff202-120">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ff202-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="ff202-121">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>
