---
title: 1029 - ScheduleFaultWorkItem
ms.date: 03/30/2017
ms.assetid: 3a56b29e-f740-459d-8576-d81e58bf5a03
ms.openlocfilehash: f5beab91f7dd39a3f8ed3b76d6c0a1ddd9bd77c3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924359"
---
# <a name="1029---schedulefaultworkitem"></a><span data-ttu-id="07379-102">1029 - ScheduleFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="07379-102">1029 - ScheduleFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="07379-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="07379-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="07379-104">ID</span><span class="sxs-lookup"><span data-stu-id="07379-104">ID</span></span>|<span data-ttu-id="07379-105">1029</span><span class="sxs-lookup"><span data-stu-id="07379-105">1029</span></span>|  
|<span data-ttu-id="07379-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="07379-106">Keywords</span></span>|<span data-ttu-id="07379-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="07379-107">WFRuntime</span></span>|  
|<span data-ttu-id="07379-108">レベル</span><span class="sxs-lookup"><span data-stu-id="07379-108">Level</span></span>|<span data-ttu-id="07379-109">詳細</span><span class="sxs-lookup"><span data-stu-id="07379-109">Verbose</span></span>|  
|<span data-ttu-id="07379-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="07379-110">Channel</span></span>|<span data-ttu-id="07379-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="07379-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="07379-112">説明</span><span class="sxs-lookup"><span data-stu-id="07379-112">Description</span></span>  
 <span data-ttu-id="07379-113">FaultWorkItem がスケジュールされていることを示します。</span><span class="sxs-lookup"><span data-stu-id="07379-113">Indicates a FaultWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="07379-114">メッセージ</span><span class="sxs-lookup"><span data-stu-id="07379-114">Message</span></span>  
 <span data-ttu-id="07379-115">Activity '%1'、DisplayName に対して FaultWorkItem がスケジュールされました: '%2'、InstanceId: '%3'。</span><span class="sxs-lookup"><span data-stu-id="07379-115">A FaultWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="07379-116">Activity '%4'、DisplayName: '%5'、InstanceId: '%6' から例外が伝達されました。</span><span class="sxs-lookup"><span data-stu-id="07379-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="07379-117">説明</span><span class="sxs-lookup"><span data-stu-id="07379-117">Details</span></span>  
  
|<span data-ttu-id="07379-118">データ項目名</span><span class="sxs-lookup"><span data-stu-id="07379-118">Data Item Name</span></span>|<span data-ttu-id="07379-119">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="07379-119">Data Item Type</span></span>|<span data-ttu-id="07379-120">説明</span><span class="sxs-lookup"><span data-stu-id="07379-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="07379-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="07379-121">FaultActivity</span></span>|<span data-ttu-id="07379-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="07379-122">xs:string</span></span>|<span data-ttu-id="07379-123">エラーとなったアクティビティの型名。</span><span class="sxs-lookup"><span data-stu-id="07379-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="07379-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="07379-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="07379-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="07379-125">xs:string</span></span>|<span data-ttu-id="07379-126">エラーとなったアクティビティの表示名。</span><span class="sxs-lookup"><span data-stu-id="07379-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="07379-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="07379-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="07379-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="07379-128">xs:string</span></span>|<span data-ttu-id="07379-129">エラーとなったアクティビティのインスタンス ID。</span><span class="sxs-lookup"><span data-stu-id="07379-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="07379-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="07379-130">ExceptionActivity</span></span>|<span data-ttu-id="07379-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="07379-131">xs:string</span></span>|<span data-ttu-id="07379-132">例外をスローしたアクティビティの型名。</span><span class="sxs-lookup"><span data-stu-id="07379-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="07379-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="07379-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="07379-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="07379-134">xs:string</span></span>|<span data-ttu-id="07379-135">例外をスローしたアクティビティの表示名。</span><span class="sxs-lookup"><span data-stu-id="07379-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="07379-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="07379-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="07379-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="07379-137">xs:string</span></span>|<span data-ttu-id="07379-138">例外をスローしたアクティビティのインスタンス ID。</span><span class="sxs-lookup"><span data-stu-id="07379-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="07379-139">例外</span><span class="sxs-lookup"><span data-stu-id="07379-139">Exception</span></span>|<span data-ttu-id="07379-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="07379-140">xs:string</span></span>|<span data-ttu-id="07379-141">例外の詳細</span><span class="sxs-lookup"><span data-stu-id="07379-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="07379-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="07379-142">AppDomain</span></span>|<span data-ttu-id="07379-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="07379-143">xs:string</span></span>|<span data-ttu-id="07379-144">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="07379-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
