---
title: 1015 - StartCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 96fd1d4e-c5d0-46ad-8a71-4b4b49ac7262
ms.openlocfilehash: 6a2d4c866ec7d43e8ae40b5616a97c3b7adf1843
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62032267"
---
# <a name="1015---startcompletionworkitem"></a><span data-ttu-id="8ca26-102">1015 - StartCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="8ca26-102">1015 - StartCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="8ca26-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="8ca26-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8ca26-104">ID</span><span class="sxs-lookup"><span data-stu-id="8ca26-104">ID</span></span>|<span data-ttu-id="8ca26-105">1015</span><span class="sxs-lookup"><span data-stu-id="8ca26-105">1015</span></span>|  
|<span data-ttu-id="8ca26-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="8ca26-106">Keywords</span></span>|<span data-ttu-id="8ca26-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="8ca26-107">WFRuntime</span></span>|  
|<span data-ttu-id="8ca26-108">レベル</span><span class="sxs-lookup"><span data-stu-id="8ca26-108">Level</span></span>|<span data-ttu-id="8ca26-109">詳細</span><span class="sxs-lookup"><span data-stu-id="8ca26-109">Verbose</span></span>|  
|<span data-ttu-id="8ca26-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="8ca26-110">Channel</span></span>|<span data-ttu-id="8ca26-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="8ca26-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8ca26-112">説明</span><span class="sxs-lookup"><span data-stu-id="8ca26-112">Description</span></span>  
 <span data-ttu-id="8ca26-113">CompletionWorkItem が実行を開始していることを示します。</span><span class="sxs-lookup"><span data-stu-id="8ca26-113">Indicates a CompletionWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8ca26-114">メッセージ</span><span class="sxs-lookup"><span data-stu-id="8ca26-114">Message</span></span>  
 <span data-ttu-id="8ca26-115">親 Activity '%1'、DisplayName: '%2'、InstanceId: '%3' の CompletionWorkItem の実行を開始しています。</span><span class="sxs-lookup"><span data-stu-id="8ca26-115">Starting execution of a CompletionWorkItem for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="8ca26-116">Activity '%4'、DisplayName: '%5'、InstanceId: '%6' が完了しました。</span><span class="sxs-lookup"><span data-stu-id="8ca26-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8ca26-117">説明</span><span class="sxs-lookup"><span data-stu-id="8ca26-117">Details</span></span>  
  
|<span data-ttu-id="8ca26-118">データ項目名</span><span class="sxs-lookup"><span data-stu-id="8ca26-118">Data Item Name</span></span>|<span data-ttu-id="8ca26-119">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="8ca26-119">Data Item Type</span></span>|<span data-ttu-id="8ca26-120">説明</span><span class="sxs-lookup"><span data-stu-id="8ca26-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8ca26-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="8ca26-121">ParentActivity</span></span>|<span data-ttu-id="8ca26-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="8ca26-122">xs:string</span></span>|<span data-ttu-id="8ca26-123">親アクティビティの型名。</span><span class="sxs-lookup"><span data-stu-id="8ca26-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="8ca26-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="8ca26-124">ParentDisplayName</span></span>|<span data-ttu-id="8ca26-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="8ca26-125">xs:string</span></span>|<span data-ttu-id="8ca26-126">親アクティビティの表示名。</span><span class="sxs-lookup"><span data-stu-id="8ca26-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="8ca26-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="8ca26-127">ParentInstanceId</span></span>|<span data-ttu-id="8ca26-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="8ca26-128">xs:string</span></span>|<span data-ttu-id="8ca26-129">親アクティビティのインスタンス ID。</span><span class="sxs-lookup"><span data-stu-id="8ca26-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="8ca26-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="8ca26-130">CompletedActivity</span></span>|<span data-ttu-id="8ca26-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="8ca26-131">xs:string</span></span>|<span data-ttu-id="8ca26-132">完了したアクティビティの型名。</span><span class="sxs-lookup"><span data-stu-id="8ca26-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="8ca26-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="8ca26-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="8ca26-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="8ca26-134">xs:string</span></span>|<span data-ttu-id="8ca26-135">完了したアクティビティの表示名。</span><span class="sxs-lookup"><span data-stu-id="8ca26-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="8ca26-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="8ca26-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="8ca26-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="8ca26-137">xs:string</span></span>|<span data-ttu-id="8ca26-138">完了したアクティビティのインスタンス ID。</span><span class="sxs-lookup"><span data-stu-id="8ca26-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="8ca26-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="8ca26-139">AppDomain</span></span>|<span data-ttu-id="8ca26-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="8ca26-140">xs:string</span></span>|<span data-ttu-id="8ca26-141">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="8ca26-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
