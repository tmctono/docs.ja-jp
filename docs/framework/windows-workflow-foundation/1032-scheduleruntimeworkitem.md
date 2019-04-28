---
title: 1032 - ScheduleRuntimeWorkItem
ms.date: 03/30/2017
ms.assetid: 54688101-becf-42f3-80ca-f53a7b527620
ms.openlocfilehash: 505b852d54e256b2c2bfff8d90944dd4e993e0c0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924866"
---
# <a name="1032---scheduleruntimeworkitem"></a><span data-ttu-id="0d061-102">1032 - ScheduleRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="0d061-102">1032 - ScheduleRuntimeWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="0d061-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="0d061-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0d061-104">ID</span><span class="sxs-lookup"><span data-stu-id="0d061-104">ID</span></span>|<span data-ttu-id="0d061-105">1032</span><span class="sxs-lookup"><span data-stu-id="0d061-105">1032</span></span>|  
|<span data-ttu-id="0d061-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="0d061-106">Keywords</span></span>|<span data-ttu-id="0d061-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="0d061-107">WFRuntime</span></span>|  
|<span data-ttu-id="0d061-108">レベル</span><span class="sxs-lookup"><span data-stu-id="0d061-108">Level</span></span>|<span data-ttu-id="0d061-109">詳細</span><span class="sxs-lookup"><span data-stu-id="0d061-109">Verbose</span></span>|  
|<span data-ttu-id="0d061-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="0d061-110">Channel</span></span>|<span data-ttu-id="0d061-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="0d061-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0d061-112">説明</span><span class="sxs-lookup"><span data-stu-id="0d061-112">Description</span></span>  
 <span data-ttu-id="0d061-113">RuntimeWorkItem がスケジュールされていることを示します。</span><span class="sxs-lookup"><span data-stu-id="0d061-113">Indicates a RuntimeWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0d061-114">メッセージ</span><span class="sxs-lookup"><span data-stu-id="0d061-114">Message</span></span>  
 <span data-ttu-id="0d061-115">Activity '%1'、DisplayName: '%2'、InstanceId: '%3' に対してランタイム作業項目がスケジュールされました。</span><span class="sxs-lookup"><span data-stu-id="0d061-115">A runtime work item has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0d061-116">説明</span><span class="sxs-lookup"><span data-stu-id="0d061-116">Details</span></span>  
  
|<span data-ttu-id="0d061-117">データ項目名</span><span class="sxs-lookup"><span data-stu-id="0d061-117">Data Item Name</span></span>|<span data-ttu-id="0d061-118">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="0d061-118">Data Item Type</span></span>|<span data-ttu-id="0d061-119">説明</span><span class="sxs-lookup"><span data-stu-id="0d061-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0d061-120">アクティビティ</span><span class="sxs-lookup"><span data-stu-id="0d061-120">Activity</span></span>|<span data-ttu-id="0d061-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="0d061-121">xs:string</span></span>|<span data-ttu-id="0d061-122">アクティビティの型名。</span><span class="sxs-lookup"><span data-stu-id="0d061-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="0d061-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="0d061-123">DisplayName</span></span>|<span data-ttu-id="0d061-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="0d061-124">xs:string</span></span>|<span data-ttu-id="0d061-125">アクティビティの表示名。</span><span class="sxs-lookup"><span data-stu-id="0d061-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="0d061-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="0d061-126">InstanceId</span></span>|<span data-ttu-id="0d061-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="0d061-127">xs:string</span></span>|<span data-ttu-id="0d061-128">アクティビティのインスタンス ID。</span><span class="sxs-lookup"><span data-stu-id="0d061-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="0d061-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0d061-129">AppDomain</span></span>|<span data-ttu-id="0d061-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="0d061-130">xs:string</span></span>|<span data-ttu-id="0d061-131">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="0d061-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
