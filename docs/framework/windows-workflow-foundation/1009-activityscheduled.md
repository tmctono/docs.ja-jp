---
title: 1009 - ActivityScheduled
ms.date: 03/30/2017
ms.assetid: 307e38b6-d47e-47a4-9708-e74d8314b1a1
ms.openlocfilehash: 0e3ea53a7b0509fcb8b73b61193742d615ac7e91
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924658"
---
# <a name="1009---activityscheduled"></a><span data-ttu-id="00ea2-102">1009 - ActivityScheduled</span><span class="sxs-lookup"><span data-stu-id="00ea2-102">1009 - ActivityScheduled</span></span>
## <a name="properties"></a><span data-ttu-id="00ea2-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="00ea2-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="00ea2-104">ID</span><span class="sxs-lookup"><span data-stu-id="00ea2-104">ID</span></span>|<span data-ttu-id="00ea2-105">1009</span><span class="sxs-lookup"><span data-stu-id="00ea2-105">1009</span></span>|  
|<span data-ttu-id="00ea2-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="00ea2-106">Keywords</span></span>|<span data-ttu-id="00ea2-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="00ea2-107">WFRuntime</span></span>|  
|<span data-ttu-id="00ea2-108">レベル</span><span class="sxs-lookup"><span data-stu-id="00ea2-108">Level</span></span>|<span data-ttu-id="00ea2-109">情報</span><span class="sxs-lookup"><span data-stu-id="00ea2-109">Information</span></span>|  
|<span data-ttu-id="00ea2-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="00ea2-110">Channel</span></span>|<span data-ttu-id="00ea2-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="00ea2-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="00ea2-112">説明</span><span class="sxs-lookup"><span data-stu-id="00ea2-112">Description</span></span>  
 <span data-ttu-id="00ea2-113">アクティビティの実行がスケジュールされていることを示します。</span><span class="sxs-lookup"><span data-stu-id="00ea2-113">Indicates an activity is being scheduled for execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="00ea2-114">メッセージ</span><span class="sxs-lookup"><span data-stu-id="00ea2-114">Message</span></span>  
 <span data-ttu-id="00ea2-115">Parent Activity '%1'、DisplayName: '%2'、InstanceId: '%3' scheduled child Activity '%4'、DisplayName: '%5'、InstanceId: '%6'。</span><span class="sxs-lookup"><span data-stu-id="00ea2-115">Parent Activity '%1', DisplayName: '%2', InstanceId: '%3' scheduled child Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="00ea2-116">説明</span><span class="sxs-lookup"><span data-stu-id="00ea2-116">Details</span></span>  
  
|<span data-ttu-id="00ea2-117">データ項目名</span><span class="sxs-lookup"><span data-stu-id="00ea2-117">Data Item Name</span></span>|<span data-ttu-id="00ea2-118">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="00ea2-118">Data Item Type</span></span>|<span data-ttu-id="00ea2-119">説明</span><span class="sxs-lookup"><span data-stu-id="00ea2-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="00ea2-120">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="00ea2-120">ParentActivity</span></span>|<span data-ttu-id="00ea2-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="00ea2-121">xs:string</span></span>|<span data-ttu-id="00ea2-122">親アクティビティの型名。</span><span class="sxs-lookup"><span data-stu-id="00ea2-122">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="00ea2-123">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="00ea2-123">ParentDisplayName</span></span>|<span data-ttu-id="00ea2-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="00ea2-124">xs:string</span></span>|<span data-ttu-id="00ea2-125">親アクティビティの表示名。</span><span class="sxs-lookup"><span data-stu-id="00ea2-125">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="00ea2-126">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="00ea2-126">ParentInstanceId</span></span>|<span data-ttu-id="00ea2-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="00ea2-127">xs:string</span></span>|<span data-ttu-id="00ea2-128">親アクティビティのインスタンス ID。</span><span class="sxs-lookup"><span data-stu-id="00ea2-128">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="00ea2-129">ChildActivity</span><span class="sxs-lookup"><span data-stu-id="00ea2-129">ChildActivity</span></span>|<span data-ttu-id="00ea2-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="00ea2-130">xs:string</span></span>|<span data-ttu-id="00ea2-131">スケジュール済みの子アクティビティの型名。</span><span class="sxs-lookup"><span data-stu-id="00ea2-131">The type name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="00ea2-132">ChildDisplayName</span><span class="sxs-lookup"><span data-stu-id="00ea2-132">ChildDisplayName</span></span>|<span data-ttu-id="00ea2-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="00ea2-133">xs:string</span></span>|<span data-ttu-id="00ea2-134">スケジュール済みの子アクティビティの表示名。</span><span class="sxs-lookup"><span data-stu-id="00ea2-134">The display name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="00ea2-135">ChildInstanceId</span><span class="sxs-lookup"><span data-stu-id="00ea2-135">ChildInstanceId</span></span>|<span data-ttu-id="00ea2-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="00ea2-136">xs:string</span></span>|<span data-ttu-id="00ea2-137">スケジュール済み子アクティビティのインスタンス ID。</span><span class="sxs-lookup"><span data-stu-id="00ea2-137">The instance id of the scheduled child activity.</span></span>|  
|<span data-ttu-id="00ea2-138">AppDomain</span><span class="sxs-lookup"><span data-stu-id="00ea2-138">AppDomain</span></span>|<span data-ttu-id="00ea2-139">xs:string</span><span class="sxs-lookup"><span data-stu-id="00ea2-139">xs:string</span></span>|<span data-ttu-id="00ea2-140">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="00ea2-140">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
