---
title: <timeOuts>
ms.date: 03/30/2017
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
ms.openlocfilehash: b6ae5faa2dd2ffef9669a0245a75227b0f669cf7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59118067"
---
# <a name="timeouts"></a><span data-ttu-id="d4deb-101">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="d4deb-101">\<timeOuts></span></span>
<span data-ttu-id="d4deb-102">サービス ホストを開くまたは閉じるまでに待機できる期間を指定する構成要素を表します。</span><span class="sxs-lookup"><span data-stu-id="d4deb-102">Represents a configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>  
  
 <span data-ttu-id="d4deb-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="d4deb-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="d4deb-104">\<client></span><span class="sxs-lookup"><span data-stu-id="d4deb-104">\<client></span></span>  
<span data-ttu-id="d4deb-105">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="d4deb-105">\<endpoint></span></span>  
<span data-ttu-id="d4deb-106">\<host></span><span class="sxs-lookup"><span data-stu-id="d4deb-106">\<host></span></span>  
<span data-ttu-id="d4deb-107">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="d4deb-107">\<timeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4deb-108">構文</span><span class="sxs-lookup"><span data-stu-id="d4deb-108">Syntax</span></span>  
  
```xml  
<timeOuts closeTimeout="TimeSpan"
          openTimeout="TimeSpan" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d4deb-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d4deb-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d4deb-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d4deb-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d4deb-111">属性</span><span class="sxs-lookup"><span data-stu-id="d4deb-111">Attributes</span></span>  
  
|<span data-ttu-id="d4deb-112">属性</span><span class="sxs-lookup"><span data-stu-id="d4deb-112">Attribute</span></span>|<span data-ttu-id="d4deb-113">説明</span><span class="sxs-lookup"><span data-stu-id="d4deb-113">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="d4deb-114">サービス ホストを閉じるまでに待機できる期間を指定する <xref:System.TimeSpan> 値。</span><span class="sxs-lookup"><span data-stu-id="d4deb-114">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to close.</span></span>|  
|`openTimeout`|<span data-ttu-id="d4deb-115">サービス ホストを開くまでに待機できる期間を指定する <xref:System.TimeSpan> 値。</span><span class="sxs-lookup"><span data-stu-id="d4deb-115">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to open.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d4deb-116">子要素</span><span class="sxs-lookup"><span data-stu-id="d4deb-116">Child Elements</span></span>  
 <span data-ttu-id="d4deb-117">なし。</span><span class="sxs-lookup"><span data-stu-id="d4deb-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d4deb-118">親要素</span><span class="sxs-lookup"><span data-stu-id="d4deb-118">Parent Elements</span></span>  
  
|<span data-ttu-id="d4deb-119">要素</span><span class="sxs-lookup"><span data-stu-id="d4deb-119">Element</span></span>|<span data-ttu-id="d4deb-120">説明</span><span class="sxs-lookup"><span data-stu-id="d4deb-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d4deb-121">\<host></span><span class="sxs-lookup"><span data-stu-id="d4deb-121">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="d4deb-122">サービス ホストの設定を指定する構成要素です。</span><span class="sxs-lookup"><span data-stu-id="d4deb-122">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d4deb-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="d4deb-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="d4deb-124">ホスト</span><span class="sxs-lookup"><span data-stu-id="d4deb-124">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
