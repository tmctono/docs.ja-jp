---
title: 215 - MessageReceivedByTransport
ms.date: 03/30/2017
ms.assetid: bb32aa60-5207-4711-9f08-110e8ac327e5
ms.openlocfilehash: aa1ad30526aa65501e5d9875d3877631ca00879b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964187"
---
# <a name="215---messagereceivedbytransport"></a><span data-ttu-id="4df9f-102">215 - MessageReceivedByTransport</span><span class="sxs-lookup"><span data-stu-id="4df9f-102">215 - MessageReceivedByTransport</span></span>
## <a name="properties"></a><span data-ttu-id="4df9f-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="4df9f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4df9f-104">ID</span><span class="sxs-lookup"><span data-stu-id="4df9f-104">ID</span></span>|<span data-ttu-id="4df9f-105">215</span><span class="sxs-lookup"><span data-stu-id="4df9f-105">215</span></span>|  
|<span data-ttu-id="4df9f-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="4df9f-106">Keywords</span></span>|<span data-ttu-id="4df9f-107">Troubleshooting、ServiceModel</span><span class="sxs-lookup"><span data-stu-id="4df9f-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="4df9f-108">レベル</span><span class="sxs-lookup"><span data-stu-id="4df9f-108">Level</span></span>|<span data-ttu-id="4df9f-109">[情報]</span><span class="sxs-lookup"><span data-stu-id="4df9f-109">Information</span></span>|  
|<span data-ttu-id="4df9f-110">Channel</span><span class="sxs-lookup"><span data-stu-id="4df9f-110">Channel</span></span>|<span data-ttu-id="4df9f-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="4df9f-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4df9f-112">説明</span><span class="sxs-lookup"><span data-stu-id="4df9f-112">Description</span></span>  
 <span data-ttu-id="4df9f-113">このイベントは、TCP ベースのトランスポートがメッセージを受信するときに発生します。</span><span class="sxs-lookup"><span data-stu-id="4df9f-113">This event occurs when a TCP-based transport receives a message.</span></span> <span data-ttu-id="4df9f-114">トランスポート レベルでは、1 つの操作に対して複数のメッセージが、クライアントとサービス間で交換されることがあります。</span><span class="sxs-lookup"><span data-stu-id="4df9f-114">Note that at the transport level, multiple messages can be exchanged between clients and services for a single operation.</span></span> <span data-ttu-id="4df9f-115">これはインフラストラクチャの動作によるもので、セキュリティがその一例です。</span><span class="sxs-lookup"><span data-stu-id="4df9f-115">This can be due to infrastructure behavior, security is a good example.</span></span> <span data-ttu-id="4df9f-116">そのため、生成される `MessageReceivedByTransport` イベントの数が、サービスのバインディングとその構成に応じて異なります。</span><span class="sxs-lookup"><span data-stu-id="4df9f-116">Therefore, the number of `MessageReceivedByTransport` events that are emitted vary based on your service's binding and its configuration.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4df9f-117">一方向トランスポートでは、このイベントは発生しません。</span><span class="sxs-lookup"><span data-stu-id="4df9f-117">This event is not emitted for one-way transports.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4df9f-118">Message</span><span class="sxs-lookup"><span data-stu-id="4df9f-118">Message</span></span>  
 <span data-ttu-id="4df9f-119">トランスポートが '%1' からメッセージを受信しました。</span><span class="sxs-lookup"><span data-stu-id="4df9f-119">The transport received a message from '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="4df9f-120">説明</span><span class="sxs-lookup"><span data-stu-id="4df9f-120">Details</span></span>  
  
|<span data-ttu-id="4df9f-121">データ項目名</span><span class="sxs-lookup"><span data-stu-id="4df9f-121">Data Item Name</span></span>|<span data-ttu-id="4df9f-122">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="4df9f-122">Data Item Type</span></span>|<span data-ttu-id="4df9f-123">説明</span><span class="sxs-lookup"><span data-stu-id="4df9f-123">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4df9f-124">Listen Address</span><span class="sxs-lookup"><span data-stu-id="4df9f-124">Listen Address</span></span>|`xs:string`|<span data-ttu-id="4df9f-125">メッセージを受信したアドレス。</span><span class="sxs-lookup"><span data-stu-id="4df9f-125">The address that received the message.</span></span>|  
|<span data-ttu-id="4df9f-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="4df9f-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="4df9f-127">Web ホスト サービスの場合は、このフィールドにより、サービスが Web 階層内で一意に識別されます。</span><span class="sxs-lookup"><span data-stu-id="4df9f-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="4df9f-128">この形式は、' Web サイト名アプリケーション仮想パス&#124;サービスの仮想パス&#124;ServiceName ' として定義されています。</span><span class="sxs-lookup"><span data-stu-id="4df9f-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="4df9f-129">例:' 既定の Web サイト/計算 Atorapplication&#124;&#124;/計算 atoratorservice '。</span><span class="sxs-lookup"><span data-stu-id="4df9f-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="4df9f-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="4df9f-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="4df9f-131">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="4df9f-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
