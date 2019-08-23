---
title: <backupLists>
ms.date: 03/30/2017
ms.assetid: 593b3390-f65b-4684-ad40-0596b62f0954
ms.openlocfilehash: b65cc4d04b5304e93b70509c9db3bc2248accb7f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926437"
---
# <a name="backuplists"></a><span data-ttu-id="7a28d-101">\<backupLists ></span><span class="sxs-lookup"><span data-stu-id="7a28d-101">\<backupLists></span></span>
<span data-ttu-id="7a28d-102">エラー処理に使用されるバックアップ サービス セットを定義する構成セクションを表します。</span><span class="sxs-lookup"><span data-stu-id="7a28d-102">Represents a configuration section for defining a set of backup services used in error handling.</span></span> <span data-ttu-id="7a28d-103">各子要素は、プライマリエンドポイントに到達できない場合にルーティングサービスによって使用される一連のエンドポイントを列挙するバックアップリストです。</span><span class="sxs-lookup"><span data-stu-id="7a28d-103">Each child element is a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="7a28d-104">リストの最初のエンドポイントがダウンしていると、ルーティング サービスは自動的にリスト内で次にあるエンドポイントにフェールオーバーします。</span><span class="sxs-lookup"><span data-stu-id="7a28d-104">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="7a28d-105">これにより、クライアント アプリケーションに複雑なパターンの処理方法やサービスの配置場所を示すことなく、アプリケーションの信頼性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="7a28d-105">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
 <span data-ttu-id="7a28d-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="7a28d-106">\<system.serviceModel></span></span>  
<span data-ttu-id="7a28d-107">\<ルーティング ></span><span class="sxs-lookup"><span data-stu-id="7a28d-107">\<routing></span></span>  
<span data-ttu-id="7a28d-108">\<backupLists ></span><span class="sxs-lookup"><span data-stu-id="7a28d-108">\<backupLists></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a28d-109">構文</span><span class="sxs-lookup"><span data-stu-id="7a28d-109">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7a28d-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="7a28d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7a28d-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="7a28d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7a28d-112">属性</span><span class="sxs-lookup"><span data-stu-id="7a28d-112">Attributes</span></span>  
 <span data-ttu-id="7a28d-113">なし。</span><span class="sxs-lookup"><span data-stu-id="7a28d-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7a28d-114">子要素</span><span class="sxs-lookup"><span data-stu-id="7a28d-114">Child Elements</span></span>  
  
|<span data-ttu-id="7a28d-115">要素</span><span class="sxs-lookup"><span data-stu-id="7a28d-115">Element</span></span>|<span data-ttu-id="7a28d-116">説明</span><span class="sxs-lookup"><span data-stu-id="7a28d-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7a28d-117">\<filter></span><span class="sxs-lookup"><span data-stu-id="7a28d-117">\<filter></span></span>](filter.md)|<span data-ttu-id="7a28d-118">プライマリエンドポイントに到達できない場合に、ルーティングサービスで使用するエンドポイントの一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7a28d-118">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="7a28d-119">.</span><span class="sxs-lookup"><span data-stu-id="7a28d-119">.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7a28d-120">親要素</span><span class="sxs-lookup"><span data-stu-id="7a28d-120">Parent Elements</span></span>  
  
|<span data-ttu-id="7a28d-121">要素</span><span class="sxs-lookup"><span data-stu-id="7a28d-121">Element</span></span>|<span data-ttu-id="7a28d-122">説明</span><span class="sxs-lookup"><span data-stu-id="7a28d-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7a28d-123">\<ルーティング ></span><span class="sxs-lookup"><span data-stu-id="7a28d-123">\<routing></span></span>](routing.md)|<span data-ttu-id="7a28d-124">一連のルーティングフィルターを定義するための構成セクションを表します。これにより、受信メッセージ<xref:System.ServiceModel.Dispatcher.MessageFilter>を評価するときに使用する Windows Communication Foundation (WCF) の種類、およびターゲットエンドポイントを定義するルーティングテーブルを決定します。フィルターが一致したときにメッセージをに送信します。</span><span class="sxs-lookup"><span data-stu-id="7a28d-124">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7a28d-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="7a28d-125">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
