---
title: 3550 - BufferOutOfOrderMessageNoInstance
ms.date: 03/30/2017
ms.assetid: 1299d294-99b8-430e-98b1-55f5f17002f3
ms.openlocfilehash: 1af943e23aa643c6614b946175c0b1854a7ceb62
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61755585"
---
# <a name="3550---bufferoutofordermessagenoinstance"></a><span data-ttu-id="40044-102">3550 - BufferOutOfOrderMessageNoInstance</span><span class="sxs-lookup"><span data-stu-id="40044-102">3550 - BufferOutOfOrderMessageNoInstance</span></span>
## <a name="properties"></a><span data-ttu-id="40044-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="40044-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="40044-104">ID</span><span class="sxs-lookup"><span data-stu-id="40044-104">ID</span></span>|<span data-ttu-id="40044-105">3550</span><span class="sxs-lookup"><span data-stu-id="40044-105">3550</span></span>|  
|<span data-ttu-id="40044-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="40044-106">Keywords</span></span>|<span data-ttu-id="40044-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="40044-107">WFServices</span></span>|  
|<span data-ttu-id="40044-108">レベル</span><span class="sxs-lookup"><span data-stu-id="40044-108">Level</span></span>|<span data-ttu-id="40044-109">情報</span><span class="sxs-lookup"><span data-stu-id="40044-109">Information</span></span>|  
|<span data-ttu-id="40044-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="40044-110">Channel</span></span>|<span data-ttu-id="40044-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="40044-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="40044-112">説明</span><span class="sxs-lookup"><span data-stu-id="40044-112">Description</span></span>  
 <span data-ttu-id="40044-113">バッファーされた受信機能が失敗したことを示します。</span><span class="sxs-lookup"><span data-stu-id="40044-113">Indicates a buffered receive has failed.</span></span> <span data-ttu-id="40044-114">サービス インスタンスがこの特定の操作を処理する準備が整った場合、操作が再試行されます。</span><span class="sxs-lookup"><span data-stu-id="40044-114">The operation will be attempted again when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="40044-115">メッセージ</span><span class="sxs-lookup"><span data-stu-id="40044-115">Message</span></span>  
 <span data-ttu-id="40044-116">操作 '%1' は現時点では実行できません。</span><span class="sxs-lookup"><span data-stu-id="40044-116">Operation '%1' cannot be performed at this time.</span></span> <span data-ttu-id="40044-117">サービス インスタンスがこの特定の操作を処理できる状態になったとき、もう一度試行されます。</span><span class="sxs-lookup"><span data-stu-id="40044-117">Another attempt will be made when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="40044-118">説明</span><span class="sxs-lookup"><span data-stu-id="40044-118">Details</span></span>  
  
|<span data-ttu-id="40044-119">データ項目名</span><span class="sxs-lookup"><span data-stu-id="40044-119">Data Item Name</span></span>|<span data-ttu-id="40044-120">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="40044-120">Data Item Type</span></span>|<span data-ttu-id="40044-121">説明</span><span class="sxs-lookup"><span data-stu-id="40044-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="40044-122">OperationName</span><span class="sxs-lookup"><span data-stu-id="40044-122">OperationName</span></span>|<span data-ttu-id="40044-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="40044-123">xs:string</span></span>|<span data-ttu-id="40044-124">操作の名前。</span><span class="sxs-lookup"><span data-stu-id="40044-124">The name of the operation.</span></span>|  
|<span data-ttu-id="40044-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="40044-125">AppDomain</span></span>|<span data-ttu-id="40044-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="40044-126">xs:string</span></span>|<span data-ttu-id="40044-127">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="40044-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
