---
title: 1012 - StartExecuteActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 29e9b1c6-c5d7-4b58-b59d-a06a923d3c80
ms.openlocfilehash: d6b330bc454c39584e5027f757fd9d9d3434d941
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924580"
---
# <a name="1012---startexecuteactivityworkitem"></a><span data-ttu-id="04b2a-102">1012 - StartExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="04b2a-102">1012 - StartExecuteActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="04b2a-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="04b2a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="04b2a-104">ID</span><span class="sxs-lookup"><span data-stu-id="04b2a-104">ID</span></span>|<span data-ttu-id="04b2a-105">1012</span><span class="sxs-lookup"><span data-stu-id="04b2a-105">1012</span></span>|  
|<span data-ttu-id="04b2a-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="04b2a-106">Keywords</span></span>|<span data-ttu-id="04b2a-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="04b2a-107">WFRuntime</span></span>|  
|<span data-ttu-id="04b2a-108">レベル</span><span class="sxs-lookup"><span data-stu-id="04b2a-108">Level</span></span>|<span data-ttu-id="04b2a-109">詳細</span><span class="sxs-lookup"><span data-stu-id="04b2a-109">Verbose</span></span>|  
|<span data-ttu-id="04b2a-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="04b2a-110">Channel</span></span>|<span data-ttu-id="04b2a-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="04b2a-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="04b2a-112">説明</span><span class="sxs-lookup"><span data-stu-id="04b2a-112">Description</span></span>  
 <span data-ttu-id="04b2a-113">ExecuteActivityWorkItem が実行を開始していることを示します。</span><span class="sxs-lookup"><span data-stu-id="04b2a-113">Indicates an ExecuteActivityWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="04b2a-114">メッセージ</span><span class="sxs-lookup"><span data-stu-id="04b2a-114">Message</span></span>  
 <span data-ttu-id="04b2a-115">Activity '%1'、DisplayName: '%2'、InstanceId: '%3' の ExecuteActivityWorkItem の実行を開始しています。</span><span class="sxs-lookup"><span data-stu-id="04b2a-115">Starting execution of an ExecuteActivityWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="04b2a-116">説明</span><span class="sxs-lookup"><span data-stu-id="04b2a-116">Details</span></span>  
  
|<span data-ttu-id="04b2a-117">データ項目名</span><span class="sxs-lookup"><span data-stu-id="04b2a-117">Data Item Name</span></span>|<span data-ttu-id="04b2a-118">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="04b2a-118">Data Item Type</span></span>|<span data-ttu-id="04b2a-119">説明</span><span class="sxs-lookup"><span data-stu-id="04b2a-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="04b2a-120">アクティビティ</span><span class="sxs-lookup"><span data-stu-id="04b2a-120">Activity</span></span>|<span data-ttu-id="04b2a-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="04b2a-121">xs:string</span></span>|<span data-ttu-id="04b2a-122">アクティビティの型名。</span><span class="sxs-lookup"><span data-stu-id="04b2a-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="04b2a-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="04b2a-123">DisplayName</span></span>|<span data-ttu-id="04b2a-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="04b2a-124">xs:string</span></span>|<span data-ttu-id="04b2a-125">アクティビティの表示名。</span><span class="sxs-lookup"><span data-stu-id="04b2a-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="04b2a-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="04b2a-126">InstanceId</span></span>|<span data-ttu-id="04b2a-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="04b2a-127">xs:string</span></span>|<span data-ttu-id="04b2a-128">アクティビティのインスタンス ID。</span><span class="sxs-lookup"><span data-stu-id="04b2a-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="04b2a-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="04b2a-129">AppDomain</span></span>|<span data-ttu-id="04b2a-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="04b2a-130">xs:string</span></span>|<span data-ttu-id="04b2a-131">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="04b2a-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
