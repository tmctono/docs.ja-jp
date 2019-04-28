---
title: 1035 - RuntimeTransactionSet
ms.date: 03/30/2017
ms.assetid: 03b37de9-778c-4beb-b0e3-de73ece6088e
ms.openlocfilehash: 198e11dd94b0ad5cdc1e01c3611280754ca081d3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924853"
---
# <a name="1035---runtimetransactionset"></a><span data-ttu-id="37aba-102">1035 - RuntimeTransactionSet</span><span class="sxs-lookup"><span data-stu-id="37aba-102">1035 - RuntimeTransactionSet</span></span>
## <a name="properties"></a><span data-ttu-id="37aba-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="37aba-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="37aba-104">ID</span><span class="sxs-lookup"><span data-stu-id="37aba-104">ID</span></span>|<span data-ttu-id="37aba-105">1035</span><span class="sxs-lookup"><span data-stu-id="37aba-105">1035</span></span>|  
|<span data-ttu-id="37aba-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="37aba-106">Keywords</span></span>|<span data-ttu-id="37aba-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="37aba-107">WFRuntime</span></span>|  
|<span data-ttu-id="37aba-108">レベル</span><span class="sxs-lookup"><span data-stu-id="37aba-108">Level</span></span>|<span data-ttu-id="37aba-109">詳細</span><span class="sxs-lookup"><span data-stu-id="37aba-109">Verbose</span></span>|  
|<span data-ttu-id="37aba-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="37aba-110">Channel</span></span>|<span data-ttu-id="37aba-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="37aba-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="37aba-112">説明</span><span class="sxs-lookup"><span data-stu-id="37aba-112">Description</span></span>  
 <span data-ttu-id="37aba-113">アクティビティがランタイムのトランザクションを設定したことを示します。</span><span class="sxs-lookup"><span data-stu-id="37aba-113">Indicates an activity has set the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="37aba-114">メッセージ</span><span class="sxs-lookup"><span data-stu-id="37aba-114">Message</span></span>  
 <span data-ttu-id="37aba-115">Activity '%1'、DisplayName によってランタイム トランザクションが設定されています: '%2'、InstanceId: '%3'。</span><span class="sxs-lookup"><span data-stu-id="37aba-115">The runtime transaction has been set by Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="37aba-116">実行の分離を Activity '%4'、DisplayName: '%5'、InstanceId: '%6'。</span><span class="sxs-lookup"><span data-stu-id="37aba-116">Execution isolated to Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="37aba-117">説明</span><span class="sxs-lookup"><span data-stu-id="37aba-117">Details</span></span>  
  
|<span data-ttu-id="37aba-118">データ項目名</span><span class="sxs-lookup"><span data-stu-id="37aba-118">Data Item Name</span></span>|<span data-ttu-id="37aba-119">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="37aba-119">Data Item Type</span></span>|<span data-ttu-id="37aba-120">説明</span><span class="sxs-lookup"><span data-stu-id="37aba-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="37aba-121">アクティビティ</span><span class="sxs-lookup"><span data-stu-id="37aba-121">Activity</span></span>|<span data-ttu-id="37aba-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="37aba-122">xs:string</span></span>|<span data-ttu-id="37aba-123">アクティビティの型名。</span><span class="sxs-lookup"><span data-stu-id="37aba-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="37aba-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="37aba-124">DisplayName</span></span>|<span data-ttu-id="37aba-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="37aba-125">xs:string</span></span>|<span data-ttu-id="37aba-126">アクティビティの表示名。</span><span class="sxs-lookup"><span data-stu-id="37aba-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="37aba-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="37aba-127">InstanceId</span></span>|<span data-ttu-id="37aba-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="37aba-128">xs:string</span></span>|<span data-ttu-id="37aba-129">アクティビティのインスタンス ID。</span><span class="sxs-lookup"><span data-stu-id="37aba-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="37aba-130">IsolatedActivity</span><span class="sxs-lookup"><span data-stu-id="37aba-130">IsolatedActivity</span></span>|<span data-ttu-id="37aba-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="37aba-131">xs:string</span></span>|<span data-ttu-id="37aba-132">トランザクションが分離されるアクティビティの型の名前。</span><span class="sxs-lookup"><span data-stu-id="37aba-132">The type name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="37aba-133">IsolatedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="37aba-133">IsolatedActivityDisplayName</span></span>|<span data-ttu-id="37aba-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="37aba-134">xs:string</span></span>|<span data-ttu-id="37aba-135">トランザクションが分離されるアクティビティの表示名。</span><span class="sxs-lookup"><span data-stu-id="37aba-135">The display name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="37aba-136">IsolatedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="37aba-136">IsolatedActivityInstanceId</span></span>|<span data-ttu-id="37aba-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="37aba-137">xs:string</span></span>|<span data-ttu-id="37aba-138">トランザクションが分離されるアクティビティのインスタンスの ID。</span><span class="sxs-lookup"><span data-stu-id="37aba-138">The instance id of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="37aba-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="37aba-139">AppDomain</span></span>|<span data-ttu-id="37aba-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="37aba-140">xs:string</span></span>|<span data-ttu-id="37aba-141">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="37aba-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
