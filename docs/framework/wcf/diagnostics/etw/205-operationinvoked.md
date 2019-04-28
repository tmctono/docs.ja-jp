---
title: 205 - OperationInvoked
ms.date: 03/30/2017
ms.assetid: 9c8d6c90-dfa5-4ae0-a589-96679a8fb3ba
ms.openlocfilehash: e95b6923d21307b2ef68d4a5369b3cee86540239
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781980"
---
# <a name="205---operationinvoked"></a><span data-ttu-id="a47fa-102">205 - OperationInvoked</span><span class="sxs-lookup"><span data-stu-id="a47fa-102">205 - OperationInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="a47fa-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="a47fa-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a47fa-104">ID</span><span class="sxs-lookup"><span data-stu-id="a47fa-104">ID</span></span>|<span data-ttu-id="a47fa-105">205</span><span class="sxs-lookup"><span data-stu-id="a47fa-105">205</span></span>|  
|<span data-ttu-id="a47fa-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="a47fa-106">Keywords</span></span>|<span data-ttu-id="a47fa-107">Troubleshooting、ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a47fa-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="a47fa-108">レベル</span><span class="sxs-lookup"><span data-stu-id="a47fa-108">Level</span></span>|<span data-ttu-id="a47fa-109">情報</span><span class="sxs-lookup"><span data-stu-id="a47fa-109">Information</span></span>|  
|<span data-ttu-id="a47fa-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="a47fa-110">Channel</span></span>|<span data-ttu-id="a47fa-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="a47fa-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a47fa-112">説明</span><span class="sxs-lookup"><span data-stu-id="a47fa-112">Description</span></span>  
 <span data-ttu-id="a47fa-113">このイベントは、サービス モデルの既定の `OperationInvoker` がメソッドの呼び出しを開始する直前に生成されます。</span><span class="sxs-lookup"><span data-stu-id="a47fa-113">This event is emitted just before the Service Model's default `OperationInvoker` begins a call to a method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a47fa-114">メッセージ</span><span class="sxs-lookup"><span data-stu-id="a47fa-114">Message</span></span>  
 <span data-ttu-id="a47fa-115">OperationInvoker が '%1' メソッドを呼び出しました。</span><span class="sxs-lookup"><span data-stu-id="a47fa-115">An OperationInvoker invoked the '%1' method.</span></span> <span data-ttu-id="a47fa-116">呼び出し元の情報: '%2'。</span><span class="sxs-lookup"><span data-stu-id="a47fa-116">Caller information: '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a47fa-117">説明</span><span class="sxs-lookup"><span data-stu-id="a47fa-117">Details</span></span>  
  
|<span data-ttu-id="a47fa-118">データ項目名</span><span class="sxs-lookup"><span data-stu-id="a47fa-118">Data Item Name</span></span>|<span data-ttu-id="a47fa-119">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="a47fa-119">Data Item Type</span></span>|<span data-ttu-id="a47fa-120">説明</span><span class="sxs-lookup"><span data-stu-id="a47fa-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a47fa-121">メソッド名</span><span class="sxs-lookup"><span data-stu-id="a47fa-121">Method Name</span></span>|`xs:string`|<span data-ttu-id="a47fa-122">`OperationInvoker` によって呼び出されたメソッドの CLR 名。</span><span class="sxs-lookup"><span data-stu-id="a47fa-122">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="a47fa-123">呼び出し元情報</span><span class="sxs-lookup"><span data-stu-id="a47fa-123">Caller Information</span></span>|`xs:string`|<span data-ttu-id="a47fa-124">クライアントの IP アドレスとポート番号。'&lt;IP アドレス&gt;:&lt;ポート番号&gt;' の形式で指定します。</span><span class="sxs-lookup"><span data-stu-id="a47fa-124">The IP address and port number of the client in the format 'IPAddress:PortNumber'.</span></span> <span data-ttu-id="a47fa-125">この 2 つの値は、操作コンテキスト内の 'System.ServiceModel.Channels.RemoteEndpointMessageProperty' メッセージ プロパティから取得します。</span><span class="sxs-lookup"><span data-stu-id="a47fa-125">The two values are retrieved from the 'System.ServiceModel.Channels.RemoteEndpointMessageProperty' message property within the operation context.</span></span> <span data-ttu-id="a47fa-126">TCP 以外のバインドの場合、この値は `null` になることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a47fa-126">Note that for non-TCP bindings this value `null`.</span></span>|  
|<span data-ttu-id="a47fa-127">HostReference</span><span class="sxs-lookup"><span data-stu-id="a47fa-127">HostReference</span></span>|`xs:string`|<span data-ttu-id="a47fa-128">Web ホスト サービスの場合は、このフィールドにより、サービスが Web 階層内で一意に識別されます。</span><span class="sxs-lookup"><span data-stu-id="a47fa-128">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="a47fa-129">その形式が定義されている ' Web サイト名アプリケーション仮想パス&#124;サービス仮想パス&#124;ServiceName'。</span><span class="sxs-lookup"><span data-stu-id="a47fa-129">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="a47fa-130">例:' 既定の Web サイト/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'。</span><span class="sxs-lookup"><span data-stu-id="a47fa-130">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="a47fa-131">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a47fa-131">AppDomain</span></span>|`xs:string`|<span data-ttu-id="a47fa-132">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="a47fa-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
