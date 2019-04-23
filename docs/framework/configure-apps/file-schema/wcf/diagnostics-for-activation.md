---
title: <diagnostics> アクティブ化
ms.date: 03/30/2017
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
ms.openlocfilehash: 30456963a7d74a93e39bb1fddc0910daae97f039
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59203809"
---
# <a name="diagnostics-for-activation"></a><span data-ttu-id="49667-102">\<診断 > アクティブ化</span><span class="sxs-lookup"><span data-stu-id="49667-102">\<diagnostics> for Activation</span></span>
<span data-ttu-id="49667-103">Windows Communication Foundation (WCF) リスナーの診断機能を構成します。</span><span class="sxs-lookup"><span data-stu-id="49667-103">Configures Windows Communication Foundation (WCF) listener's diagnostics functionalities.</span></span>  
  
 <span data-ttu-id="49667-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="49667-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="49667-105">\<diagnostics></span><span class="sxs-lookup"><span data-stu-id="49667-105">\<diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49667-106">構文</span><span class="sxs-lookup"><span data-stu-id="49667-106">Syntax</span></span>  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <diagnostics performanceCountersEnabled="Boolean" />
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a><span data-ttu-id="49667-107">型</span><span class="sxs-lookup"><span data-stu-id="49667-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="49667-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="49667-108">Attributes and Elements</span></span>  
 <span data-ttu-id="49667-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="49667-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="49667-110">属性</span><span class="sxs-lookup"><span data-stu-id="49667-110">Attributes</span></span>  
  
|<span data-ttu-id="49667-111">属性</span><span class="sxs-lookup"><span data-stu-id="49667-111">Attribute</span></span>|<span data-ttu-id="49667-112">説明</span><span class="sxs-lookup"><span data-stu-id="49667-112">Description</span></span>|  
|---------------|-----------------|  
|`performanceCountersEnabled`|<span data-ttu-id="49667-113">診断用パフォーマンス カウンターが有効であるかどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="49667-113">A Boolean value that indicates whether performance counters are enabled for diagnostic purposes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="49667-114">子要素</span><span class="sxs-lookup"><span data-stu-id="49667-114">Child Elements</span></span>  
 <span data-ttu-id="49667-115">なし。</span><span class="sxs-lookup"><span data-stu-id="49667-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="49667-116">親要素</span><span class="sxs-lookup"><span data-stu-id="49667-116">Parent Elements</span></span>  
  
|<span data-ttu-id="49667-117">要素</span><span class="sxs-lookup"><span data-stu-id="49667-117">Element</span></span>|<span data-ttu-id="49667-118">説明</span><span class="sxs-lookup"><span data-stu-id="49667-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="49667-119">\<system.serviceModel.activation ></span><span class="sxs-lookup"><span data-stu-id="49667-119">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|<span data-ttu-id="49667-120">リスナー プロセス SMSvcHost.exe の設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="49667-120">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="49667-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="49667-121">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>
