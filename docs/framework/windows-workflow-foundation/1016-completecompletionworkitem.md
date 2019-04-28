---
title: 1016 - CompleteCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 246929fb-6f14-440a-814b-cd8349350644
ms.openlocfilehash: 3f0904a561a242cd3be528c9707a409b6f98e0fe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61925087"
---
# <a name="1016---completecompletionworkitem"></a><span data-ttu-id="83903-102">1016 - CompleteCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="83903-102">1016 - CompleteCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="83903-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="83903-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="83903-104">ID</span><span class="sxs-lookup"><span data-stu-id="83903-104">ID</span></span>|<span data-ttu-id="83903-105">1016</span><span class="sxs-lookup"><span data-stu-id="83903-105">1016</span></span>|  
|<span data-ttu-id="83903-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="83903-106">Keywords</span></span>|<span data-ttu-id="83903-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="83903-107">WFRuntime</span></span>|  
|<span data-ttu-id="83903-108">レベル</span><span class="sxs-lookup"><span data-stu-id="83903-108">Level</span></span>|<span data-ttu-id="83903-109">詳細</span><span class="sxs-lookup"><span data-stu-id="83903-109">Verbose</span></span>|  
|<span data-ttu-id="83903-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="83903-110">Channel</span></span>|<span data-ttu-id="83903-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="83903-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="83903-112">説明</span><span class="sxs-lookup"><span data-stu-id="83903-112">Description</span></span>  
 <span data-ttu-id="83903-113">CompletionWorkItem が完了したことを示します。</span><span class="sxs-lookup"><span data-stu-id="83903-113">Indicates a CompletionWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="83903-114">メッセージ</span><span class="sxs-lookup"><span data-stu-id="83903-114">Message</span></span>  
 <span data-ttu-id="83903-115">親 Activity '%1'、DisplayName: '%2'、InstanceId: '%3' の CompletionWorkItem が完了しました。</span><span class="sxs-lookup"><span data-stu-id="83903-115">A CompletionWorkItem has completed for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="83903-116">Activity '%4'、DisplayName: '%5'、InstanceId: '%6' が完了しました。</span><span class="sxs-lookup"><span data-stu-id="83903-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="83903-117">説明</span><span class="sxs-lookup"><span data-stu-id="83903-117">Details</span></span>  
  
|<span data-ttu-id="83903-118">データ項目名</span><span class="sxs-lookup"><span data-stu-id="83903-118">Data Item Name</span></span>|<span data-ttu-id="83903-119">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="83903-119">Data Item Type</span></span>|<span data-ttu-id="83903-120">説明</span><span class="sxs-lookup"><span data-stu-id="83903-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="83903-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="83903-121">ParentActivity</span></span>|<span data-ttu-id="83903-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="83903-122">xs:string</span></span>|<span data-ttu-id="83903-123">親アクティビティの型名。</span><span class="sxs-lookup"><span data-stu-id="83903-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="83903-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="83903-124">ParentDisplayName</span></span>|<span data-ttu-id="83903-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="83903-125">xs:string</span></span>|<span data-ttu-id="83903-126">親アクティビティの表示名。</span><span class="sxs-lookup"><span data-stu-id="83903-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="83903-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="83903-127">ParentInstanceId</span></span>|<span data-ttu-id="83903-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="83903-128">xs:string</span></span>|<span data-ttu-id="83903-129">親アクティビティのインスタンス ID。</span><span class="sxs-lookup"><span data-stu-id="83903-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="83903-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="83903-130">CompletedActivity</span></span>|<span data-ttu-id="83903-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="83903-131">xs:string</span></span>|<span data-ttu-id="83903-132">完了したアクティビティの型名。</span><span class="sxs-lookup"><span data-stu-id="83903-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="83903-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="83903-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="83903-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="83903-134">xs:string</span></span>|<span data-ttu-id="83903-135">完了したアクティビティの表示名。</span><span class="sxs-lookup"><span data-stu-id="83903-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="83903-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="83903-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="83903-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="83903-137">xs:string</span></span>|<span data-ttu-id="83903-138">完了したアクティビティのインスタンス ID。</span><span class="sxs-lookup"><span data-stu-id="83903-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="83903-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="83903-139">AppDomain</span></span>|<span data-ttu-id="83903-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="83903-140">xs:string</span></span>|<span data-ttu-id="83903-141">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="83903-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
