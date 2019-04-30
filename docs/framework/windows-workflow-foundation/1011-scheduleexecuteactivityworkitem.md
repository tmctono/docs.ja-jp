---
title: 1011 - ScheduleExecuteActivityWorkItem
ms.date: 03/30/2017
ms.assetid: e503ae46-ad6b-4fcb-8c0e-146d59a8eff1
ms.openlocfilehash: 299d09b7c4db94a2e27378ba0cc3dfeb03734ab4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61982255"
---
# <a name="1011---scheduleexecuteactivityworkitem"></a><span data-ttu-id="bcc8c-102">1011 - ScheduleExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="bcc8c-102">1011 - ScheduleExecuteActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="bcc8c-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="bcc8c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bcc8c-104">ID</span><span class="sxs-lookup"><span data-stu-id="bcc8c-104">ID</span></span>|<span data-ttu-id="bcc8c-105">1011</span><span class="sxs-lookup"><span data-stu-id="bcc8c-105">1011</span></span>|  
|<span data-ttu-id="bcc8c-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="bcc8c-106">Keywords</span></span>|<span data-ttu-id="bcc8c-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="bcc8c-107">WFRuntime</span></span>|  
|<span data-ttu-id="bcc8c-108">レベル</span><span class="sxs-lookup"><span data-stu-id="bcc8c-108">Level</span></span>|<span data-ttu-id="bcc8c-109">詳細</span><span class="sxs-lookup"><span data-stu-id="bcc8c-109">Verbose</span></span>|  
|<span data-ttu-id="bcc8c-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="bcc8c-110">Channel</span></span>|<span data-ttu-id="bcc8c-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="bcc8c-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="bcc8c-112">説明</span><span class="sxs-lookup"><span data-stu-id="bcc8c-112">Description</span></span>  
 <span data-ttu-id="bcc8c-113">ExecuteActivityWorkItem がスケジュールされたことを示します。</span><span class="sxs-lookup"><span data-stu-id="bcc8c-113">Indicates an ExecuteActivityWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="bcc8c-114">メッセージ</span><span class="sxs-lookup"><span data-stu-id="bcc8c-114">Message</span></span>  
 <span data-ttu-id="bcc8c-115">Activity '%1'、DisplayName: '%2'、InstanceId: '%3' に対して ExecuteActivityWorkItem がスケジュールされました。</span><span class="sxs-lookup"><span data-stu-id="bcc8c-115">An ExecuteActivityWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="bcc8c-116">説明</span><span class="sxs-lookup"><span data-stu-id="bcc8c-116">Details</span></span>  
  
|<span data-ttu-id="bcc8c-117">データ項目名</span><span class="sxs-lookup"><span data-stu-id="bcc8c-117">Data Item Name</span></span>|<span data-ttu-id="bcc8c-118">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="bcc8c-118">Data Item Type</span></span>|<span data-ttu-id="bcc8c-119">説明</span><span class="sxs-lookup"><span data-stu-id="bcc8c-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="bcc8c-120">アクティビティ</span><span class="sxs-lookup"><span data-stu-id="bcc8c-120">Activity</span></span>|<span data-ttu-id="bcc8c-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="bcc8c-121">xs:string</span></span>|<span data-ttu-id="bcc8c-122">アクティビティの型名。</span><span class="sxs-lookup"><span data-stu-id="bcc8c-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="bcc8c-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="bcc8c-123">DisplayName</span></span>|<span data-ttu-id="bcc8c-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="bcc8c-124">xs:string</span></span>|<span data-ttu-id="bcc8c-125">アクティビティの表示名。</span><span class="sxs-lookup"><span data-stu-id="bcc8c-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="bcc8c-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="bcc8c-126">InstanceId</span></span>|<span data-ttu-id="bcc8c-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="bcc8c-127">xs:string</span></span>|<span data-ttu-id="bcc8c-128">アクティビティのインスタンス ID。</span><span class="sxs-lookup"><span data-stu-id="bcc8c-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="bcc8c-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="bcc8c-129">AppDomain</span></span>|<span data-ttu-id="bcc8c-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="bcc8c-130">xs:string</span></span>|<span data-ttu-id="bcc8c-131">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="bcc8c-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
