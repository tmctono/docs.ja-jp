---
title: 1021 - ScheduleBookmarkWorkItem
ms.date: 03/30/2017
ms.assetid: 2e0da311-b219-4637-9460-90cdafcc4ecd
ms.openlocfilehash: abc026165568d05faef619da28c94f27f37eea27
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924424"
---
# <a name="1021---schedulebookmarkworkitem"></a><span data-ttu-id="c03de-102">1021 - ScheduleBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="c03de-102">1021 - ScheduleBookmarkWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="c03de-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c03de-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c03de-104">ID</span><span class="sxs-lookup"><span data-stu-id="c03de-104">ID</span></span>|<span data-ttu-id="c03de-105">1021</span><span class="sxs-lookup"><span data-stu-id="c03de-105">1021</span></span>|  
|<span data-ttu-id="c03de-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="c03de-106">Keywords</span></span>|<span data-ttu-id="c03de-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="c03de-107">WFRuntime</span></span>|  
|<span data-ttu-id="c03de-108">レベル</span><span class="sxs-lookup"><span data-stu-id="c03de-108">Level</span></span>|<span data-ttu-id="c03de-109">詳細</span><span class="sxs-lookup"><span data-stu-id="c03de-109">Verbose</span></span>|  
|<span data-ttu-id="c03de-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="c03de-110">Channel</span></span>|<span data-ttu-id="c03de-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="c03de-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c03de-112">説明</span><span class="sxs-lookup"><span data-stu-id="c03de-112">Description</span></span>  
 <span data-ttu-id="c03de-113">BookmarkWorkItem がスケジュールされていることを示します。</span><span class="sxs-lookup"><span data-stu-id="c03de-113">Indicates a BookmarkWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c03de-114">メッセージ</span><span class="sxs-lookup"><span data-stu-id="c03de-114">Message</span></span>  
 <span data-ttu-id="c03de-115">Activity '%1'、DisplayName に対して BookmarkWorkItem がスケジュールされました: '%2'、InstanceId: '%3'。</span><span class="sxs-lookup"><span data-stu-id="c03de-115">A BookmarkWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="c03de-116">BookmarkName: %4、BookmarkScope: %5。</span><span class="sxs-lookup"><span data-stu-id="c03de-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c03de-117">説明</span><span class="sxs-lookup"><span data-stu-id="c03de-117">Details</span></span>  
  
|<span data-ttu-id="c03de-118">データ項目名</span><span class="sxs-lookup"><span data-stu-id="c03de-118">Data Item Name</span></span>|<span data-ttu-id="c03de-119">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="c03de-119">Data Item Type</span></span>|<span data-ttu-id="c03de-120">説明</span><span class="sxs-lookup"><span data-stu-id="c03de-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c03de-121">アクティビティ</span><span class="sxs-lookup"><span data-stu-id="c03de-121">Activity</span></span>|<span data-ttu-id="c03de-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="c03de-122">xs:string</span></span>|<span data-ttu-id="c03de-123">アクティビティの型名。</span><span class="sxs-lookup"><span data-stu-id="c03de-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="c03de-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="c03de-124">DisplayName</span></span>|<span data-ttu-id="c03de-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="c03de-125">xs:string</span></span>|<span data-ttu-id="c03de-126">アクティビティの表示名。</span><span class="sxs-lookup"><span data-stu-id="c03de-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="c03de-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="c03de-127">InstanceId</span></span>|<span data-ttu-id="c03de-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="c03de-128">xs:string</span></span>|<span data-ttu-id="c03de-129">アクティビティのインスタンス ID。</span><span class="sxs-lookup"><span data-stu-id="c03de-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="c03de-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="c03de-130">BookmarkName</span></span>|<span data-ttu-id="c03de-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="c03de-131">xs:string</span></span>|<span data-ttu-id="c03de-132">ブックマークの名前。</span><span class="sxs-lookup"><span data-stu-id="c03de-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="c03de-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="c03de-133">BookmarkScope</span></span>|<span data-ttu-id="c03de-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="c03de-134">xs:string</span></span>|<span data-ttu-id="c03de-135">ブックマークのスコープ。</span><span class="sxs-lookup"><span data-stu-id="c03de-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="c03de-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="c03de-136">AppDomain</span></span>|<span data-ttu-id="c03de-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="c03de-137">xs:string</span></span>|<span data-ttu-id="c03de-138">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="c03de-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
