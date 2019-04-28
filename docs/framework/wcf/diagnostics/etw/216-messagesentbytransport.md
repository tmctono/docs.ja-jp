---
title: 216 - MessageSentByTransport
ms.date: 03/30/2017
ms.assetid: 150c3167-4154-4225-8d94-57cc94341233
ms.openlocfilehash: fa21568e4c8c38eefe359c417d47ec0a9d30a7c4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781811"
---
# <a name="216---messagesentbytransport"></a><span data-ttu-id="4f110-102">216 - MessageSentByTransport</span><span class="sxs-lookup"><span data-stu-id="4f110-102">216 - MessageSentByTransport</span></span>
## <a name="properties"></a><span data-ttu-id="4f110-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="4f110-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4f110-104">ID</span><span class="sxs-lookup"><span data-stu-id="4f110-104">ID</span></span>|<span data-ttu-id="4f110-105">216</span><span class="sxs-lookup"><span data-stu-id="4f110-105">216</span></span>|  
|<span data-ttu-id="4f110-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="4f110-106">Keywords</span></span>|<span data-ttu-id="4f110-107">Troubleshooting、ServiceModel</span><span class="sxs-lookup"><span data-stu-id="4f110-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="4f110-108">レベル</span><span class="sxs-lookup"><span data-stu-id="4f110-108">Level</span></span>|<span data-ttu-id="4f110-109">情報</span><span class="sxs-lookup"><span data-stu-id="4f110-109">Information</span></span>|  
|<span data-ttu-id="4f110-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="4f110-110">Channel</span></span>|<span data-ttu-id="4f110-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="4f110-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4f110-112">説明</span><span class="sxs-lookup"><span data-stu-id="4f110-112">Description</span></span>  
 <span data-ttu-id="4f110-113">このイベントは、TCP ベースのトランスポートがメッセージを送信するときに発生します。</span><span class="sxs-lookup"><span data-stu-id="4f110-113">This event occurs when a TCP-based transport sends a message.</span></span> <span data-ttu-id="4f110-114">トランスポート レベルでは、1 つの操作に対して複数のメッセージが、クライアントとサービス間で交換されることがあります。</span><span class="sxs-lookup"><span data-stu-id="4f110-114">Note that at the transport level multiple messages can be exchanged between clients and services for a single operation.</span></span> <span data-ttu-id="4f110-115">これはインフラストラクチャの動作によるもので、セキュリティがその一例です。</span><span class="sxs-lookup"><span data-stu-id="4f110-115">This may be due to infrastructure behavior, security being a good example.</span></span> <span data-ttu-id="4f110-116">そのため、数**MessageSentByTransport**が生成されるイベントは、サービスのバインディングとその構成に基づいて異なります。</span><span class="sxs-lookup"><span data-stu-id="4f110-116">Therefore, the number of **MessageSentByTransport** events that are emitted vary based on your service's binding and its configuration.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4f110-117">メッセージ</span><span class="sxs-lookup"><span data-stu-id="4f110-117">Message</span></span>  
 <span data-ttu-id="4f110-118">トランスポートが '%1' にメッセージを送信しました。</span><span class="sxs-lookup"><span data-stu-id="4f110-118">The transport sent a message to '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="4f110-119">説明</span><span class="sxs-lookup"><span data-stu-id="4f110-119">Details</span></span>  
  
|<span data-ttu-id="4f110-120">データ項目名</span><span class="sxs-lookup"><span data-stu-id="4f110-120">Data Item Name</span></span>|<span data-ttu-id="4f110-121">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="4f110-121">Data Item Type</span></span>|<span data-ttu-id="4f110-122">説明</span><span class="sxs-lookup"><span data-stu-id="4f110-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4f110-123">DestinationAddress</span><span class="sxs-lookup"><span data-stu-id="4f110-123">DestinationAddress</span></span>|`xs:string`|<span data-ttu-id="4f110-124">要求メッセージが送信されたアドレス。</span><span class="sxs-lookup"><span data-stu-id="4f110-124">The address that the request message was sent to.</span></span>|  
|<span data-ttu-id="4f110-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="4f110-125">HostReference</span></span>|<span data-ttu-id="4f110-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="4f110-126">xs:string</span></span>|<span data-ttu-id="4f110-127">Web ホスト サービスの場合は、このフィールドにより、サービスが Web 階層内で一意に識別されます。</span><span class="sxs-lookup"><span data-stu-id="4f110-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="4f110-128">その形式が定義されている ' Web サイト名アプリケーション仮想パス&#124;サービス仮想パス&#124;ServiceName'。</span><span class="sxs-lookup"><span data-stu-id="4f110-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="4f110-129">例:' 既定の Web サイト/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'。</span><span class="sxs-lookup"><span data-stu-id="4f110-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="4f110-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="4f110-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="4f110-131">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="4f110-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
