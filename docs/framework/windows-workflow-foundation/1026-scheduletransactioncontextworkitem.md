---
title: 1026 - ScheduleTransactionContextWorkItem
ms.date: 03/30/2017
ms.assetid: 0d5f86ba-ec21-4129-a726-5432e425384c
ms.openlocfilehash: 6d0b43208f86c52e8863d4415a64466b0531832c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924632"
---
# <a name="1026---scheduletransactioncontextworkitem"></a><span data-ttu-id="45894-102">1026 - ScheduleTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="45894-102">1026 - ScheduleTransactionContextWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="45894-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="45894-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="45894-104">ID</span><span class="sxs-lookup"><span data-stu-id="45894-104">ID</span></span>|<span data-ttu-id="45894-105">1026</span><span class="sxs-lookup"><span data-stu-id="45894-105">1026</span></span>|  
|<span data-ttu-id="45894-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="45894-106">Keywords</span></span>|<span data-ttu-id="45894-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="45894-107">WFRuntime</span></span>|  
|<span data-ttu-id="45894-108">レベル</span><span class="sxs-lookup"><span data-stu-id="45894-108">Level</span></span>|<span data-ttu-id="45894-109">詳細</span><span class="sxs-lookup"><span data-stu-id="45894-109">Verbose</span></span>|  
|<span data-ttu-id="45894-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="45894-110">Channel</span></span>|<span data-ttu-id="45894-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="45894-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="45894-112">説明</span><span class="sxs-lookup"><span data-stu-id="45894-112">Description</span></span>  
 <span data-ttu-id="45894-113">TransactionContextWorkItem がスケジュールされていることを示します。</span><span class="sxs-lookup"><span data-stu-id="45894-113">Indicates a TransactionContextWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="45894-114">メッセージ</span><span class="sxs-lookup"><span data-stu-id="45894-114">Message</span></span>  
 <span data-ttu-id="45894-115">Activity '%1'、DisplayName: '%2'、InstanceId: '%3' に対して TransactionContextWorkItem がスケジュールされました。</span><span class="sxs-lookup"><span data-stu-id="45894-115">A TransactionContextWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="45894-116">説明</span><span class="sxs-lookup"><span data-stu-id="45894-116">Details</span></span>  
  
|<span data-ttu-id="45894-117">データ項目名</span><span class="sxs-lookup"><span data-stu-id="45894-117">Data Item Name</span></span>|<span data-ttu-id="45894-118">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="45894-118">Data Item Type</span></span>|<span data-ttu-id="45894-119">説明</span><span class="sxs-lookup"><span data-stu-id="45894-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="45894-120">アクティビティ</span><span class="sxs-lookup"><span data-stu-id="45894-120">Activity</span></span>|<span data-ttu-id="45894-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="45894-121">xs:string</span></span>|<span data-ttu-id="45894-122">アクティビティの型名。</span><span class="sxs-lookup"><span data-stu-id="45894-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="45894-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="45894-123">DisplayName</span></span>|<span data-ttu-id="45894-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="45894-124">xs:string</span></span>|<span data-ttu-id="45894-125">アクティビティの表示名。</span><span class="sxs-lookup"><span data-stu-id="45894-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="45894-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="45894-126">InstanceId</span></span>|<span data-ttu-id="45894-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="45894-127">xs:string</span></span>|<span data-ttu-id="45894-128">アクティビティのインスタンス ID。</span><span class="sxs-lookup"><span data-stu-id="45894-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="45894-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="45894-129">AppDomain</span></span>|<span data-ttu-id="45894-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="45894-130">xs:string</span></span>|<span data-ttu-id="45894-131">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="45894-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
