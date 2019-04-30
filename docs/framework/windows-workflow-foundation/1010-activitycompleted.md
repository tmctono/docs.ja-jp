---
title: 1010 - ActivityCompleted
ms.date: 03/30/2017
ms.assetid: d256284e-3fd2-4c33-82f4-abb617575706
ms.openlocfilehash: 355281e6aa8f621bd2f9c0862e641fafec872750
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008372"
---
# <a name="1010---activitycompleted"></a><span data-ttu-id="01aac-102">1010 - ActivityCompleted</span><span class="sxs-lookup"><span data-stu-id="01aac-102">1010 - ActivityCompleted</span></span>
## <a name="properties"></a><span data-ttu-id="01aac-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="01aac-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="01aac-104">ID</span><span class="sxs-lookup"><span data-stu-id="01aac-104">ID</span></span>|<span data-ttu-id="01aac-105">1010</span><span class="sxs-lookup"><span data-stu-id="01aac-105">1010</span></span>|  
|<span data-ttu-id="01aac-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="01aac-106">Keywords</span></span>|<span data-ttu-id="01aac-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="01aac-107">WFRuntime</span></span>|  
|<span data-ttu-id="01aac-108">レベル</span><span class="sxs-lookup"><span data-stu-id="01aac-108">Level</span></span>|<span data-ttu-id="01aac-109">情報</span><span class="sxs-lookup"><span data-stu-id="01aac-109">Information</span></span>|  
|<span data-ttu-id="01aac-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="01aac-110">Channel</span></span>|<span data-ttu-id="01aac-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="01aac-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="01aac-112">説明</span><span class="sxs-lookup"><span data-stu-id="01aac-112">Description</span></span>  
 <span data-ttu-id="01aac-113">アクティビティが実行を完了したことを示します。</span><span class="sxs-lookup"><span data-stu-id="01aac-113">Indicates an activity has completed execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="01aac-114">メッセージ</span><span class="sxs-lookup"><span data-stu-id="01aac-114">Message</span></span>  
 <span data-ttu-id="01aac-115">Activity '%1'、DisplayName: '%2'、InstanceId: '%3' が状態 '%4' で完了しました。</span><span class="sxs-lookup"><span data-stu-id="01aac-115">Activity '%1', DisplayName: '%2', InstanceId: '%3' has completed in the '%4' state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="01aac-116">説明</span><span class="sxs-lookup"><span data-stu-id="01aac-116">Details</span></span>  
  
|<span data-ttu-id="01aac-117">データ項目名</span><span class="sxs-lookup"><span data-stu-id="01aac-117">Data Item Name</span></span>|<span data-ttu-id="01aac-118">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="01aac-118">Data Item Type</span></span>|<span data-ttu-id="01aac-119">説明</span><span class="sxs-lookup"><span data-stu-id="01aac-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="01aac-120">アクティビティ</span><span class="sxs-lookup"><span data-stu-id="01aac-120">Activity</span></span>|<span data-ttu-id="01aac-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="01aac-121">xs:string</span></span>|<span data-ttu-id="01aac-122">アクティビティの型名。</span><span class="sxs-lookup"><span data-stu-id="01aac-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="01aac-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="01aac-123">DisplayName</span></span>|<span data-ttu-id="01aac-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="01aac-124">xs:string</span></span>|<span data-ttu-id="01aac-125">アクティビティの表示名。</span><span class="sxs-lookup"><span data-stu-id="01aac-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="01aac-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="01aac-126">InstanceId</span></span>|<span data-ttu-id="01aac-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="01aac-127">xs:string</span></span>|<span data-ttu-id="01aac-128">アクティビティのインスタンス ID。</span><span class="sxs-lookup"><span data-stu-id="01aac-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="01aac-129">状態</span><span class="sxs-lookup"><span data-stu-id="01aac-129">State</span></span>|<span data-ttu-id="01aac-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="01aac-130">xs:string</span></span>|<span data-ttu-id="01aac-131">アクティビティの状態。</span><span class="sxs-lookup"><span data-stu-id="01aac-131">The state of the activity.</span></span>|  
|<span data-ttu-id="01aac-132">AppDomain</span><span class="sxs-lookup"><span data-stu-id="01aac-132">AppDomain</span></span>|<span data-ttu-id="01aac-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="01aac-133">xs:string</span></span>|<span data-ttu-id="01aac-134">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="01aac-134">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
