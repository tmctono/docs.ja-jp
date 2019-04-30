---
title: 1031 - CompleteFaultWorkItem
ms.date: 03/30/2017
ms.assetid: 95f4ccb0-6be4-41f3-9330-fae43165828f
ms.openlocfilehash: cdcbe516fc8ba7440b3d109a5e5cadc105ecee9f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008799"
---
# <a name="1031---completefaultworkitem"></a><span data-ttu-id="b4e44-102">1031 - CompleteFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="b4e44-102">1031 - CompleteFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="b4e44-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="b4e44-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b4e44-104">ID</span><span class="sxs-lookup"><span data-stu-id="b4e44-104">ID</span></span>|<span data-ttu-id="b4e44-105">1031</span><span class="sxs-lookup"><span data-stu-id="b4e44-105">1031</span></span>|  
|<span data-ttu-id="b4e44-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="b4e44-106">Keywords</span></span>|<span data-ttu-id="b4e44-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="b4e44-107">WFRuntime</span></span>|  
|<span data-ttu-id="b4e44-108">レベル</span><span class="sxs-lookup"><span data-stu-id="b4e44-108">Level</span></span>|<span data-ttu-id="b4e44-109">詳細</span><span class="sxs-lookup"><span data-stu-id="b4e44-109">Verbose</span></span>|  
|<span data-ttu-id="b4e44-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="b4e44-110">Channel</span></span>|<span data-ttu-id="b4e44-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="b4e44-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b4e44-112">説明</span><span class="sxs-lookup"><span data-stu-id="b4e44-112">Description</span></span>  
 <span data-ttu-id="b4e44-113">FaultWorkItem が完了したことを示します。</span><span class="sxs-lookup"><span data-stu-id="b4e44-113">Indicates a FaultWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b4e44-114">メッセージ</span><span class="sxs-lookup"><span data-stu-id="b4e44-114">Message</span></span>  
 <span data-ttu-id="b4e44-115">Activity '%1'、DisplayName: '%2'、InstanceId: '%3' の FaultWorkItem が完了しました。</span><span class="sxs-lookup"><span data-stu-id="b4e44-115">A FaultWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="b4e44-116">Activity '%4'、DisplayName: '%5'、InstanceId: '%6' から例外が伝達されました。</span><span class="sxs-lookup"><span data-stu-id="b4e44-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b4e44-117">説明</span><span class="sxs-lookup"><span data-stu-id="b4e44-117">Details</span></span>  
  
|<span data-ttu-id="b4e44-118">データ項目名</span><span class="sxs-lookup"><span data-stu-id="b4e44-118">Data Item Name</span></span>|<span data-ttu-id="b4e44-119">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="b4e44-119">Data Item Type</span></span>|<span data-ttu-id="b4e44-120">説明</span><span class="sxs-lookup"><span data-stu-id="b4e44-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b4e44-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="b4e44-121">FaultActivity</span></span>|<span data-ttu-id="b4e44-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="b4e44-122">xs:string</span></span>|<span data-ttu-id="b4e44-123">エラーとなったアクティビティの型名。</span><span class="sxs-lookup"><span data-stu-id="b4e44-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="b4e44-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="b4e44-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="b4e44-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="b4e44-125">xs:string</span></span>|<span data-ttu-id="b4e44-126">エラーとなったアクティビティの表示名。</span><span class="sxs-lookup"><span data-stu-id="b4e44-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="b4e44-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="b4e44-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="b4e44-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="b4e44-128">xs:string</span></span>|<span data-ttu-id="b4e44-129">エラーとなったアクティビティのインスタンス ID。</span><span class="sxs-lookup"><span data-stu-id="b4e44-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="b4e44-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="b4e44-130">ExceptionActivity</span></span>|<span data-ttu-id="b4e44-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="b4e44-131">xs:string</span></span>|<span data-ttu-id="b4e44-132">例外をスローしたアクティビティの型名。</span><span class="sxs-lookup"><span data-stu-id="b4e44-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="b4e44-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="b4e44-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="b4e44-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="b4e44-134">xs:string</span></span>|<span data-ttu-id="b4e44-135">例外をスローしたアクティビティの表示名。</span><span class="sxs-lookup"><span data-stu-id="b4e44-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="b4e44-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="b4e44-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="b4e44-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="b4e44-137">xs:string</span></span>|<span data-ttu-id="b4e44-138">例外をスローしたアクティビティのインスタンス ID。</span><span class="sxs-lookup"><span data-stu-id="b4e44-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="b4e44-139">例外</span><span class="sxs-lookup"><span data-stu-id="b4e44-139">Exception</span></span>|<span data-ttu-id="b4e44-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="b4e44-140">xs:string</span></span>|<span data-ttu-id="b4e44-141">例外の詳細</span><span class="sxs-lookup"><span data-stu-id="b4e44-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="b4e44-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b4e44-142">AppDomain</span></span>|<span data-ttu-id="b4e44-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="b4e44-143">xs:string</span></span>|<span data-ttu-id="b4e44-144">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="b4e44-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
