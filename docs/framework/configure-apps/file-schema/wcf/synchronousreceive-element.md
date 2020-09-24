---
title: <synchronousReceive> 要素
ms.date: 03/30/2017
ms.assetid: cc070387-3d11-4b02-a952-bc08ad2df05a
ms.openlocfilehash: 2073d115dd87d513a6e48b8b585fed4b49d5bb32
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157175"
---
# <a name="synchronousreceive-element"></a><span data-ttu-id="de26a-102">\<synchronousReceive> 要素</span><span class="sxs-lookup"><span data-stu-id="de26a-102">\<synchronousReceive> element</span></span>

<span data-ttu-id="de26a-103">この構成要素は、サービスまたはクライアント アプリケーションでメッセージを受信する場合のランタイム動作を指定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="de26a-103">This configuration element is used to specify run-time behavior for receiving messages in either a service or client application.</span></span> <span data-ttu-id="de26a-104">属性や子要素はありません。</span><span class="sxs-lookup"><span data-stu-id="de26a-104">It does not have any attributes or child elements.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<synchronousReceive>**  
  
## <a name="syntax"></a><span data-ttu-id="de26a-105">構文</span><span class="sxs-lookup"><span data-stu-id="de26a-105">Syntax</span></span>  
  
```xml  
<synchronousReceive />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="de26a-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="de26a-106">Attributes and Elements</span></span>  

 <span data-ttu-id="de26a-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="de26a-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="de26a-108">属性</span><span class="sxs-lookup"><span data-stu-id="de26a-108">Attributes</span></span>  

 <span data-ttu-id="de26a-109">なし。</span><span class="sxs-lookup"><span data-stu-id="de26a-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="de26a-110">子要素</span><span class="sxs-lookup"><span data-stu-id="de26a-110">Child Elements</span></span>  

 <span data-ttu-id="de26a-111">なし。</span><span class="sxs-lookup"><span data-stu-id="de26a-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="de26a-112">親要素</span><span class="sxs-lookup"><span data-stu-id="de26a-112">Parent Elements</span></span>  
  
|<span data-ttu-id="de26a-113">要素</span><span class="sxs-lookup"><span data-stu-id="de26a-113">Element</span></span>|<span data-ttu-id="de26a-114">説明</span><span class="sxs-lookup"><span data-stu-id="de26a-114">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="de26a-115">エンドポイントの動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="de26a-115">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="de26a-116">解説</span><span class="sxs-lookup"><span data-stu-id="de26a-116">Remarks</span></span>  

 <span data-ttu-id="de26a-117">この動作を使用して、既定の非同期受信ではなく同期受信を使用するようにチャネル リスナーに指示します。</span><span class="sxs-lookup"><span data-stu-id="de26a-117">Use this behavior to instruct the channel listener to use a synchronous receive rather than the default, asynchronous.</span></span> <span data-ttu-id="de26a-118">Windows Communication Foundation (WCF) は、受け入れられたチャネルごとに新しいスレッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="de26a-118">Windows Communication Foundation (WCF) issues a new thread to pump for each accepted channel.</span></span> <span data-ttu-id="de26a-119">チャネルが多数ある場合は、スレッドが不足する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="de26a-119">If there are a lot of channels, there is the possibility of running out of threads.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de26a-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="de26a-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.SynchronousReceiveElement>
- <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>
