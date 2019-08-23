---
title: <timeOuts>
ms.date: 03/30/2017
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
ms.openlocfilehash: b159488efa2a80a9dea625e4c6dfe2f215dfc457
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939185"
---
# <a name="timeouts"></a><span data-ttu-id="4e659-101">\<タイムアウト ></span><span class="sxs-lookup"><span data-stu-id="4e659-101">\<timeOuts></span></span>
<span data-ttu-id="4e659-102">サービス ホストを開くまたは閉じるまでに待機できる期間を指定する構成要素を表します。</span><span class="sxs-lookup"><span data-stu-id="4e659-102">Represents a configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>  
  
 <span data-ttu-id="4e659-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="4e659-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="4e659-104">\<client></span><span class="sxs-lookup"><span data-stu-id="4e659-104">\<client></span></span>  
<span data-ttu-id="4e659-105">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="4e659-105">\<endpoint></span></span>  
<span data-ttu-id="4e659-106">\<ホスト ></span><span class="sxs-lookup"><span data-stu-id="4e659-106">\<host></span></span>  
<span data-ttu-id="4e659-107">\<タイムアウト ></span><span class="sxs-lookup"><span data-stu-id="4e659-107">\<timeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e659-108">構文</span><span class="sxs-lookup"><span data-stu-id="4e659-108">Syntax</span></span>  
  
```xml  
<timeOuts closeTimeout="TimeSpan"
          openTimeout="TimeSpan" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4e659-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="4e659-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4e659-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="4e659-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4e659-111">属性</span><span class="sxs-lookup"><span data-stu-id="4e659-111">Attributes</span></span>  
  
|<span data-ttu-id="4e659-112">属性</span><span class="sxs-lookup"><span data-stu-id="4e659-112">Attribute</span></span>|<span data-ttu-id="4e659-113">説明</span><span class="sxs-lookup"><span data-stu-id="4e659-113">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="4e659-114">サービス ホストを閉じるまでに待機できる期間を指定する <xref:System.TimeSpan> 値。</span><span class="sxs-lookup"><span data-stu-id="4e659-114">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to close.</span></span>|  
|`openTimeout`|<span data-ttu-id="4e659-115">サービス ホストを開くまでに待機できる期間を指定する <xref:System.TimeSpan> 値。</span><span class="sxs-lookup"><span data-stu-id="4e659-115">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to open.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4e659-116">子要素</span><span class="sxs-lookup"><span data-stu-id="4e659-116">Child Elements</span></span>  
 <span data-ttu-id="4e659-117">なし。</span><span class="sxs-lookup"><span data-stu-id="4e659-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4e659-118">親要素</span><span class="sxs-lookup"><span data-stu-id="4e659-118">Parent Elements</span></span>  
  
|<span data-ttu-id="4e659-119">要素</span><span class="sxs-lookup"><span data-stu-id="4e659-119">Element</span></span>|<span data-ttu-id="4e659-120">説明</span><span class="sxs-lookup"><span data-stu-id="4e659-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4e659-121">\<ホスト ></span><span class="sxs-lookup"><span data-stu-id="4e659-121">\<host></span></span>](host.md)|<span data-ttu-id="4e659-122">サービス ホストの設定を指定する構成要素です。</span><span class="sxs-lookup"><span data-stu-id="4e659-122">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4e659-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="4e659-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="4e659-124">ホスティング</span><span class="sxs-lookup"><span data-stu-id="4e659-124">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
