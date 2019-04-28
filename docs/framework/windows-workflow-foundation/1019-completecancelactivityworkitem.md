---
title: 1019 - CompleteCancelActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 75a4a1ab-e5a3-4f4e-88e4-d19806e671d7
ms.openlocfilehash: 28d19742055c51ca94c36ffddf15dced7dfc14cf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924437"
---
# <a name="1019---completecancelactivityworkitem"></a><span data-ttu-id="28e07-102">1019 - CompleteCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="28e07-102">1019 - CompleteCancelActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="28e07-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="28e07-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="28e07-104">ID</span><span class="sxs-lookup"><span data-stu-id="28e07-104">ID</span></span>|<span data-ttu-id="28e07-105">1019</span><span class="sxs-lookup"><span data-stu-id="28e07-105">1019</span></span>|  
|<span data-ttu-id="28e07-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="28e07-106">Keywords</span></span>|<span data-ttu-id="28e07-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="28e07-107">WFRuntime</span></span>|  
|<span data-ttu-id="28e07-108">レベル</span><span class="sxs-lookup"><span data-stu-id="28e07-108">Level</span></span>|<span data-ttu-id="28e07-109">詳細</span><span class="sxs-lookup"><span data-stu-id="28e07-109">Verbose</span></span>|  
|<span data-ttu-id="28e07-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="28e07-110">Channel</span></span>|<span data-ttu-id="28e07-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="28e07-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="28e07-112">説明</span><span class="sxs-lookup"><span data-stu-id="28e07-112">Description</span></span>  
 <span data-ttu-id="28e07-113">CancelActivityWorkItem が完了したことを示します。</span><span class="sxs-lookup"><span data-stu-id="28e07-113">Indicates a CancelActivityWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="28e07-114">メッセージ</span><span class="sxs-lookup"><span data-stu-id="28e07-114">Message</span></span>  
 <span data-ttu-id="28e07-115">Activity '%1'、DisplayName: '%2'、InstanceId: '%3' の CancelActivityWorkItem が完了しました。</span><span class="sxs-lookup"><span data-stu-id="28e07-115">A CancelActivityWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="28e07-116">説明</span><span class="sxs-lookup"><span data-stu-id="28e07-116">Details</span></span>  
  
|<span data-ttu-id="28e07-117">データ項目名</span><span class="sxs-lookup"><span data-stu-id="28e07-117">Data Item Name</span></span>|<span data-ttu-id="28e07-118">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="28e07-118">Data Item Type</span></span>|<span data-ttu-id="28e07-119">説明</span><span class="sxs-lookup"><span data-stu-id="28e07-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="28e07-120">アクティビティ</span><span class="sxs-lookup"><span data-stu-id="28e07-120">Activity</span></span>|<span data-ttu-id="28e07-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="28e07-121">xs:string</span></span>|<span data-ttu-id="28e07-122">アクティビティの型名。</span><span class="sxs-lookup"><span data-stu-id="28e07-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="28e07-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="28e07-123">DisplayName</span></span>|<span data-ttu-id="28e07-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="28e07-124">xs:string</span></span>|<span data-ttu-id="28e07-125">アクティビティの表示名。</span><span class="sxs-lookup"><span data-stu-id="28e07-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="28e07-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="28e07-126">InstanceId</span></span>|<span data-ttu-id="28e07-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="28e07-127">xs:string</span></span>|<span data-ttu-id="28e07-128">アクティビティのインスタンス ID。</span><span class="sxs-lookup"><span data-stu-id="28e07-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="28e07-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="28e07-129">AppDomain</span></span>|<span data-ttu-id="28e07-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="28e07-130">xs:string</span></span>|<span data-ttu-id="28e07-131">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="28e07-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
