---
title: 1013 - CompleteExecuteActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 31fc57b3-ef2f-48f0-a5de-b4e2c5c9ded7
ms.openlocfilehash: c1ff62bb4143bb798ea7adb7c3fee539ef68bc37
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61925191"
---
# <a name="1013---completeexecuteactivityworkitem"></a><span data-ttu-id="0a714-102">1013 - CompleteExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="0a714-102">1013 - CompleteExecuteActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="0a714-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="0a714-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0a714-104">ID</span><span class="sxs-lookup"><span data-stu-id="0a714-104">ID</span></span>|<span data-ttu-id="0a714-105">1013</span><span class="sxs-lookup"><span data-stu-id="0a714-105">1013</span></span>|  
|<span data-ttu-id="0a714-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="0a714-106">Keywords</span></span>|<span data-ttu-id="0a714-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="0a714-107">WFRuntime</span></span>|  
|<span data-ttu-id="0a714-108">レベル</span><span class="sxs-lookup"><span data-stu-id="0a714-108">Level</span></span>|<span data-ttu-id="0a714-109">詳細</span><span class="sxs-lookup"><span data-stu-id="0a714-109">Verbose</span></span>|  
|<span data-ttu-id="0a714-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="0a714-110">Channel</span></span>|<span data-ttu-id="0a714-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="0a714-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0a714-112">説明</span><span class="sxs-lookup"><span data-stu-id="0a714-112">Description</span></span>  
 <span data-ttu-id="0a714-113">ExecuteActivityWorkItem が完了したことを示します</span><span class="sxs-lookup"><span data-stu-id="0a714-113">Indicates an ExecuteActivityWorkItem has completed</span></span>  
  
## <a name="message"></a><span data-ttu-id="0a714-114">メッセージ</span><span class="sxs-lookup"><span data-stu-id="0a714-114">Message</span></span>  
 <span data-ttu-id="0a714-115">Activity '%1'、DisplayName: '%2'、InstanceId: '%3' の ExecuteActivityWorkItem が完了しました。</span><span class="sxs-lookup"><span data-stu-id="0a714-115">An ExecuteActivityWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0a714-116">説明</span><span class="sxs-lookup"><span data-stu-id="0a714-116">Details</span></span>  
  
|<span data-ttu-id="0a714-117">データ項目名</span><span class="sxs-lookup"><span data-stu-id="0a714-117">Data Item Name</span></span>|<span data-ttu-id="0a714-118">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="0a714-118">Data Item Type</span></span>|<span data-ttu-id="0a714-119">説明</span><span class="sxs-lookup"><span data-stu-id="0a714-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0a714-120">アクティビティ</span><span class="sxs-lookup"><span data-stu-id="0a714-120">Activity</span></span>|<span data-ttu-id="0a714-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="0a714-121">xs:string</span></span>|<span data-ttu-id="0a714-122">アクティビティの型名。</span><span class="sxs-lookup"><span data-stu-id="0a714-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="0a714-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="0a714-123">DisplayName</span></span>|<span data-ttu-id="0a714-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="0a714-124">xs:string</span></span>|<span data-ttu-id="0a714-125">アクティビティの表示名。</span><span class="sxs-lookup"><span data-stu-id="0a714-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="0a714-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="0a714-126">InstanceId</span></span>|<span data-ttu-id="0a714-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="0a714-127">xs:string</span></span>|<span data-ttu-id="0a714-128">アクティビティのインスタンス ID。</span><span class="sxs-lookup"><span data-stu-id="0a714-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="0a714-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0a714-129">AppDomain</span></span>|<span data-ttu-id="0a714-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="0a714-130">xs:string</span></span>|<span data-ttu-id="0a714-131">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="0a714-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
