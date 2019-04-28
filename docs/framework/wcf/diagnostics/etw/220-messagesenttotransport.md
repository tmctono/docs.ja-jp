---
title: 220 - MessageSentToTransport
ms.date: 03/30/2017
ms.assetid: aef4e781-240b-45bc-bff8-400053037e71
ms.openlocfilehash: 92ec664aead15470fbed576bf157d64d984ddebf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781746"
---
# <a name="220---messagesenttotransport"></a><span data-ttu-id="97ea8-102">220 - MessageSentToTransport</span><span class="sxs-lookup"><span data-stu-id="97ea8-102">220 - MessageSentToTransport</span></span>
## <a name="properties"></a><span data-ttu-id="97ea8-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="97ea8-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="97ea8-104">ID</span><span class="sxs-lookup"><span data-stu-id="97ea8-104">Id</span></span>|<span data-ttu-id="97ea8-105">220</span><span class="sxs-lookup"><span data-stu-id="97ea8-105">220</span></span>|  
|<span data-ttu-id="97ea8-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="97ea8-106">Keywords</span></span>|<span data-ttu-id="97ea8-107">EndToEndMonitoring、Troubleshooting、ServiceModel</span><span class="sxs-lookup"><span data-stu-id="97ea8-107">EndToEndMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="97ea8-108">レベル</span><span class="sxs-lookup"><span data-stu-id="97ea8-108">Level</span></span>|<span data-ttu-id="97ea8-109">情報</span><span class="sxs-lookup"><span data-stu-id="97ea8-109">Information</span></span>|  
|<span data-ttu-id="97ea8-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="97ea8-110">Channel</span></span>|<span data-ttu-id="97ea8-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="97ea8-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="97ea8-112">説明</span><span class="sxs-lookup"><span data-stu-id="97ea8-112">Description</span></span>  
 <span data-ttu-id="97ea8-113">このイベントは、サービス モデルがトランスポートにメッセージを送信すると生成されます。</span><span class="sxs-lookup"><span data-stu-id="97ea8-113">This event is emitted when the Service Model sends a message to the transport.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="97ea8-114">一方向トランスポートでは、このイベントは発生しません。</span><span class="sxs-lookup"><span data-stu-id="97ea8-114">This event will not be emitted for one-way transports.</span></span>  
  
## <a name="message"></a><span data-ttu-id="97ea8-115">メッセージ</span><span class="sxs-lookup"><span data-stu-id="97ea8-115">Message</span></span>  
 <span data-ttu-id="97ea8-116">ディスパッチャーがトランスポートにメッセージを送信しました。</span><span class="sxs-lookup"><span data-stu-id="97ea8-116">The Dispatcher sent a message to the transport.</span></span> <span data-ttu-id="97ea8-117">関連付け ID == '%1'。</span><span class="sxs-lookup"><span data-stu-id="97ea8-117">Correlation ID == '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="97ea8-118">説明</span><span class="sxs-lookup"><span data-stu-id="97ea8-118">Details</span></span>  
  
|<span data-ttu-id="97ea8-119">データ項目名</span><span class="sxs-lookup"><span data-stu-id="97ea8-119">Data Item Name</span></span>|<span data-ttu-id="97ea8-120">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="97ea8-120">Data Item Type</span></span>|<span data-ttu-id="97ea8-121">説明</span><span class="sxs-lookup"><span data-stu-id="97ea8-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="97ea8-122">Correlation ID</span><span class="sxs-lookup"><span data-stu-id="97ea8-122">Correlation ID</span></span>|`xs:GUID`|<span data-ttu-id="97ea8-123">サービスまたはクライアントからの `MessageSentToTransport` イベントを、反対側の対応する `MessageReceivedFromTransport` と関連付けるのに使用する、アクティビティ ID。</span><span class="sxs-lookup"><span data-stu-id="97ea8-123">The activity ID used to correlate a `MessageSentToTransport` event from a service or client to its corresponding `MessageReceivedFromTransport` on the other end.</span></span>|  
|<span data-ttu-id="97ea8-124">HostReference</span><span class="sxs-lookup"><span data-stu-id="97ea8-124">HostReference</span></span>|`xs:string`|<span data-ttu-id="97ea8-125">Web ホスト サービスの場合は、このフィールドにより、サービスが Web 階層内で一意に識別されます。</span><span class="sxs-lookup"><span data-stu-id="97ea8-125">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="97ea8-126">その形式が定義されている ' Web サイト名アプリケーション仮想パス&#124;サービス仮想パス&#124;ServiceName'。</span><span class="sxs-lookup"><span data-stu-id="97ea8-126">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="97ea8-127">例:' 既定の Web サイト/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'。</span><span class="sxs-lookup"><span data-stu-id="97ea8-127">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="97ea8-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="97ea8-128">AppDomain</span></span>|`xs:string`|<span data-ttu-id="97ea8-129">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="97ea8-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
