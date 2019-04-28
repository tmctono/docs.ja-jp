---
title: 1020 - CreateBookmark
ms.date: 03/30/2017
ms.assetid: 4bee948d-816f-4803-85cc-3883b5e23d10
ms.openlocfilehash: 2a382a2f12f4800cd70286a553af253e2af64c9b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924749"
---
# <a name="1020---createbookmark"></a><span data-ttu-id="0abf7-102">1020 - CreateBookmark</span><span class="sxs-lookup"><span data-stu-id="0abf7-102">1020 - CreateBookmark</span></span>
## <a name="properties"></a><span data-ttu-id="0abf7-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="0abf7-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0abf7-104">ID</span><span class="sxs-lookup"><span data-stu-id="0abf7-104">ID</span></span>|<span data-ttu-id="0abf7-105">1020</span><span class="sxs-lookup"><span data-stu-id="0abf7-105">1020</span></span>|  
|<span data-ttu-id="0abf7-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="0abf7-106">Keywords</span></span>|<span data-ttu-id="0abf7-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="0abf7-107">WFRuntime</span></span>|  
|<span data-ttu-id="0abf7-108">レベル</span><span class="sxs-lookup"><span data-stu-id="0abf7-108">Level</span></span>|<span data-ttu-id="0abf7-109">詳細</span><span class="sxs-lookup"><span data-stu-id="0abf7-109">Verbose</span></span>|  
|<span data-ttu-id="0abf7-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="0abf7-110">Channel</span></span>|<span data-ttu-id="0abf7-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="0abf7-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0abf7-112">説明</span><span class="sxs-lookup"><span data-stu-id="0abf7-112">Description</span></span>  
 <span data-ttu-id="0abf7-113">あるアクティビティ用のブックマークが作成されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="0abf7-113">Indicates a bookmark has been created for an activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0abf7-114">メッセージ</span><span class="sxs-lookup"><span data-stu-id="0abf7-114">Message</span></span>  
 <span data-ttu-id="0abf7-115">Activity '%1'、DisplayName のブックマークが作成されました: '%2'、InstanceId: '%3'。</span><span class="sxs-lookup"><span data-stu-id="0abf7-115">A Bookmark has been created for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="0abf7-116">BookmarkName: %4、BookmarkScope: %5。</span><span class="sxs-lookup"><span data-stu-id="0abf7-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0abf7-117">説明</span><span class="sxs-lookup"><span data-stu-id="0abf7-117">Details</span></span>  
  
|<span data-ttu-id="0abf7-118">データ項目名</span><span class="sxs-lookup"><span data-stu-id="0abf7-118">Data Item Name</span></span>|<span data-ttu-id="0abf7-119">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="0abf7-119">Data Item Type</span></span>|<span data-ttu-id="0abf7-120">説明</span><span class="sxs-lookup"><span data-stu-id="0abf7-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0abf7-121">アクティビティ</span><span class="sxs-lookup"><span data-stu-id="0abf7-121">Activity</span></span>|<span data-ttu-id="0abf7-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="0abf7-122">xs:string</span></span>|<span data-ttu-id="0abf7-123">アクティビティの型名。</span><span class="sxs-lookup"><span data-stu-id="0abf7-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="0abf7-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="0abf7-124">DisplayName</span></span>|<span data-ttu-id="0abf7-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="0abf7-125">xs:string</span></span>|<span data-ttu-id="0abf7-126">アクティビティの表示名。</span><span class="sxs-lookup"><span data-stu-id="0abf7-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="0abf7-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="0abf7-127">InstanceId</span></span>|<span data-ttu-id="0abf7-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="0abf7-128">xs:string</span></span>|<span data-ttu-id="0abf7-129">アクティビティのインスタンス ID。</span><span class="sxs-lookup"><span data-stu-id="0abf7-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="0abf7-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="0abf7-130">BookmarkName</span></span>|<span data-ttu-id="0abf7-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="0abf7-131">xs:string</span></span>|<span data-ttu-id="0abf7-132">ブックマークの名前。</span><span class="sxs-lookup"><span data-stu-id="0abf7-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="0abf7-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="0abf7-133">BookmarkScope</span></span>|<span data-ttu-id="0abf7-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="0abf7-134">xs:string</span></span>|<span data-ttu-id="0abf7-135">ブックマークのスコープ。</span><span class="sxs-lookup"><span data-stu-id="0abf7-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="0abf7-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0abf7-136">AppDomain</span></span>|<span data-ttu-id="0abf7-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="0abf7-137">xs:string</span></span>|<span data-ttu-id="0abf7-138">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="0abf7-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
