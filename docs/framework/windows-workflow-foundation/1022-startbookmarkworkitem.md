---
title: 1022 - StartBookmarkWorkItem
ms.date: 03/30/2017
ms.assetid: 4415fbdb-0329-4019-803f-aea66e75f3da
ms.openlocfilehash: 93d906b32b51effaa709da6763f535708cd6f821
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924723"
---
# <a name="1022---startbookmarkworkitem"></a><span data-ttu-id="8676a-102">1022 - StartBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="8676a-102">1022 - StartBookmarkWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="8676a-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="8676a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8676a-104">ID</span><span class="sxs-lookup"><span data-stu-id="8676a-104">ID</span></span>|<span data-ttu-id="8676a-105">1022</span><span class="sxs-lookup"><span data-stu-id="8676a-105">1022</span></span>|  
|<span data-ttu-id="8676a-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="8676a-106">Keywords</span></span>|<span data-ttu-id="8676a-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="8676a-107">WFRuntime</span></span>|  
|<span data-ttu-id="8676a-108">レベル</span><span class="sxs-lookup"><span data-stu-id="8676a-108">Level</span></span>|<span data-ttu-id="8676a-109">詳細</span><span class="sxs-lookup"><span data-stu-id="8676a-109">Verbose</span></span>|  
|<span data-ttu-id="8676a-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="8676a-110">Channel</span></span>|<span data-ttu-id="8676a-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="8676a-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8676a-112">説明</span><span class="sxs-lookup"><span data-stu-id="8676a-112">Description</span></span>  
 <span data-ttu-id="8676a-113">BookmarkWorkItem が実行を開始していることを示します。</span><span class="sxs-lookup"><span data-stu-id="8676a-113">Indicates a BookmarkWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8676a-114">メッセージ</span><span class="sxs-lookup"><span data-stu-id="8676a-114">Message</span></span>  
 <span data-ttu-id="8676a-115">Activity '%1'、DisplayName の BookmarkWorkItem の実行を開始: '%2'、InstanceId: '%3'。</span><span class="sxs-lookup"><span data-stu-id="8676a-115">Starting execution of a BookmarkWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="8676a-116">BookmarkName: %4、BookmarkScope: %5。</span><span class="sxs-lookup"><span data-stu-id="8676a-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8676a-117">説明</span><span class="sxs-lookup"><span data-stu-id="8676a-117">Details</span></span>  
  
|<span data-ttu-id="8676a-118">データ項目名</span><span class="sxs-lookup"><span data-stu-id="8676a-118">Data Item Name</span></span>|<span data-ttu-id="8676a-119">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="8676a-119">Data Item Type</span></span>|<span data-ttu-id="8676a-120">説明</span><span class="sxs-lookup"><span data-stu-id="8676a-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8676a-121">アクティビティ</span><span class="sxs-lookup"><span data-stu-id="8676a-121">Activity</span></span>|<span data-ttu-id="8676a-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="8676a-122">xs:string</span></span>|<span data-ttu-id="8676a-123">アクティビティの型名。</span><span class="sxs-lookup"><span data-stu-id="8676a-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="8676a-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="8676a-124">DisplayName</span></span>|<span data-ttu-id="8676a-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="8676a-125">xs:string</span></span>|<span data-ttu-id="8676a-126">アクティビティの表示名。</span><span class="sxs-lookup"><span data-stu-id="8676a-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="8676a-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="8676a-127">InstanceId</span></span>|<span data-ttu-id="8676a-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="8676a-128">xs:string</span></span>|<span data-ttu-id="8676a-129">アクティビティのインスタンス ID。</span><span class="sxs-lookup"><span data-stu-id="8676a-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="8676a-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="8676a-130">BookmarkName</span></span>|<span data-ttu-id="8676a-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="8676a-131">xs:string</span></span>|<span data-ttu-id="8676a-132">ブックマークの名前。</span><span class="sxs-lookup"><span data-stu-id="8676a-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="8676a-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="8676a-133">BookmarkScope</span></span>|<span data-ttu-id="8676a-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="8676a-134">xs:string</span></span>|<span data-ttu-id="8676a-135">ブックマークのスコープ。</span><span class="sxs-lookup"><span data-stu-id="8676a-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="8676a-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="8676a-136">AppDomain</span></span>|<span data-ttu-id="8676a-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="8676a-137">xs:string</span></span>|<span data-ttu-id="8676a-138">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="8676a-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
