---
title: 4211 - QueuingSqlRetry
ms.date: 03/30/2017
ms.assetid: df569f88-c86b-4503-840d-1399b67f4df7
ms.openlocfilehash: ede74eb642c5c2c79b90cf1458db424d9f83b087
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774245"
---
# <a name="4211---queuingsqlretry"></a><span data-ttu-id="5fa84-102">4211 - QueuingSqlRetry</span><span class="sxs-lookup"><span data-stu-id="5fa84-102">4211 - QueuingSqlRetry</span></span>
## <a name="properties"></a><span data-ttu-id="5fa84-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="5fa84-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5fa84-104">ID</span><span class="sxs-lookup"><span data-stu-id="5fa84-104">ID</span></span>|<span data-ttu-id="5fa84-105">4211</span><span class="sxs-lookup"><span data-stu-id="5fa84-105">4211</span></span>|  
|<span data-ttu-id="5fa84-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="5fa84-106">Keywords</span></span>|<span data-ttu-id="5fa84-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="5fa84-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="5fa84-108">レベル</span><span class="sxs-lookup"><span data-stu-id="5fa84-108">Level</span></span>|<span data-ttu-id="5fa84-109">警告</span><span class="sxs-lookup"><span data-stu-id="5fa84-109">Warning</span></span>|  
|<span data-ttu-id="5fa84-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="5fa84-110">Channel</span></span>|<span data-ttu-id="5fa84-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="5fa84-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5fa84-112">説明</span><span class="sxs-lookup"><span data-stu-id="5fa84-112">Description</span></span>  
 <span data-ttu-id="5fa84-113">SQL の再試行をキューに登録していることを示します。</span><span class="sxs-lookup"><span data-stu-id="5fa84-113">Indicates queuing SQL retry.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5fa84-114">メッセージ</span><span class="sxs-lookup"><span data-stu-id="5fa84-114">Message</span></span>  
 <span data-ttu-id="5fa84-115">%1 ミリ秒の遅延で SQL の再試行をキューに登録しています。</span><span class="sxs-lookup"><span data-stu-id="5fa84-115">Queuing SQL retry with delay %1 milliseconds.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5fa84-116">説明</span><span class="sxs-lookup"><span data-stu-id="5fa84-116">Details</span></span>  
  
|<span data-ttu-id="5fa84-117">データ項目名</span><span class="sxs-lookup"><span data-stu-id="5fa84-117">Data Item Name</span></span>|<span data-ttu-id="5fa84-118">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="5fa84-118">Data Item Type</span></span>|<span data-ttu-id="5fa84-119">説明</span><span class="sxs-lookup"><span data-stu-id="5fa84-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5fa84-120">Delay</span><span class="sxs-lookup"><span data-stu-id="5fa84-120">Delay</span></span>|<span data-ttu-id="5fa84-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="5fa84-121">xs:string</span></span>|<span data-ttu-id="5fa84-122">再試行の遅延。</span><span class="sxs-lookup"><span data-stu-id="5fa84-122">The delay between retries.</span></span>|  
|<span data-ttu-id="5fa84-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="5fa84-123">AppDomain</span></span>|<span data-ttu-id="5fa84-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="5fa84-124">xs:string</span></span>|<span data-ttu-id="5fa84-125">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="5fa84-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
