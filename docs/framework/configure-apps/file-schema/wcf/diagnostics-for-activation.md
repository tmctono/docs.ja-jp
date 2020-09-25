---
title: <diagnostics> アクティブ化の場合
ms.date: 03/30/2017
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
ms.openlocfilehash: c16f32357d40b9b69d52c525ce8a395a3de8fdb1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91192322"
---
# <a name="diagnostics-for-activation"></a><span data-ttu-id="89efc-102">\<diagnostics> アクティブ化の場合</span><span class="sxs-lookup"><span data-stu-id="89efc-102">\<diagnostics> for Activation</span></span>

<span data-ttu-id="89efc-103">Windows Communication Foundation (WCF) リスナーの診断機能を構成します。</span><span class="sxs-lookup"><span data-stu-id="89efc-103">Configures Windows Communication Foundation (WCF) listener's diagnostics functionalities.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<diagnostics>**  
  
## <a name="syntax"></a><span data-ttu-id="89efc-104">構文</span><span class="sxs-lookup"><span data-stu-id="89efc-104">Syntax</span></span>  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <diagnostics performanceCountersEnabled="Boolean" />
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a><span data-ttu-id="89efc-105">種類</span><span class="sxs-lookup"><span data-stu-id="89efc-105">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="89efc-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="89efc-106">Attributes and Elements</span></span>  

 <span data-ttu-id="89efc-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="89efc-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="89efc-108">属性</span><span class="sxs-lookup"><span data-stu-id="89efc-108">Attributes</span></span>  
  
|<span data-ttu-id="89efc-109">属性</span><span class="sxs-lookup"><span data-stu-id="89efc-109">Attribute</span></span>|<span data-ttu-id="89efc-110">[説明]</span><span class="sxs-lookup"><span data-stu-id="89efc-110">Description</span></span>|  
|---------------|-----------------|  
|`performanceCountersEnabled`|<span data-ttu-id="89efc-111">診断用パフォーマンス カウンターが有効であるかどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="89efc-111">A Boolean value that indicates whether performance counters are enabled for diagnostic purposes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="89efc-112">子要素</span><span class="sxs-lookup"><span data-stu-id="89efc-112">Child Elements</span></span>  

 <span data-ttu-id="89efc-113">なし。</span><span class="sxs-lookup"><span data-stu-id="89efc-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="89efc-114">親要素</span><span class="sxs-lookup"><span data-stu-id="89efc-114">Parent Elements</span></span>  
  
|<span data-ttu-id="89efc-115">要素</span><span class="sxs-lookup"><span data-stu-id="89efc-115">Element</span></span>|<span data-ttu-id="89efc-116">説明</span><span class="sxs-lookup"><span data-stu-id="89efc-116">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel.activation>](system-servicemodel-activation.md)|<span data-ttu-id="89efc-117">リスナー プロセス SMSvcHost.exe の設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="89efc-117">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="89efc-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="89efc-118">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>
