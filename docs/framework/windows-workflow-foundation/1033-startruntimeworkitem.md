---
title: 1033 - StartRuntimeWorkItem
ms.date: 03/30/2017
ms.assetid: 172b5346-9f3b-46ae-bc06-39872022376a
ms.openlocfilehash: c7192ed7c5fb43fe6f65b47b8cebde3cf4aed32c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924242"
---
# <a name="1033---startruntimeworkitem"></a><span data-ttu-id="ee79c-102">1033 - StartRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="ee79c-102">1033 - StartRuntimeWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="ee79c-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="ee79c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ee79c-104">ID</span><span class="sxs-lookup"><span data-stu-id="ee79c-104">ID</span></span>|<span data-ttu-id="ee79c-105">1033</span><span class="sxs-lookup"><span data-stu-id="ee79c-105">1033</span></span>|  
|<span data-ttu-id="ee79c-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="ee79c-106">Keywords</span></span>|<span data-ttu-id="ee79c-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="ee79c-107">WFRuntime</span></span>|  
|<span data-ttu-id="ee79c-108">レベル</span><span class="sxs-lookup"><span data-stu-id="ee79c-108">Level</span></span>|<span data-ttu-id="ee79c-109">詳細</span><span class="sxs-lookup"><span data-stu-id="ee79c-109">Verbose</span></span>|  
|<span data-ttu-id="ee79c-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="ee79c-110">Channel</span></span>|<span data-ttu-id="ee79c-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="ee79c-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ee79c-112">説明</span><span class="sxs-lookup"><span data-stu-id="ee79c-112">Description</span></span>  
 <span data-ttu-id="ee79c-113">RuntimeWorkItem が実行を開始していることを示します。</span><span class="sxs-lookup"><span data-stu-id="ee79c-113">Indicates a RuntimeWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ee79c-114">メッセージ</span><span class="sxs-lookup"><span data-stu-id="ee79c-114">Message</span></span>  
 <span data-ttu-id="ee79c-115">Activity '%1'、DisplayName: '%2'、InstanceId: '%3' のランタイム作業項目の実行を開始しています。</span><span class="sxs-lookup"><span data-stu-id="ee79c-115">Starting execution of a runtime work item for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ee79c-116">説明</span><span class="sxs-lookup"><span data-stu-id="ee79c-116">Details</span></span>  
  
|<span data-ttu-id="ee79c-117">データ項目名</span><span class="sxs-lookup"><span data-stu-id="ee79c-117">Data Item Name</span></span>|<span data-ttu-id="ee79c-118">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="ee79c-118">Data Item Type</span></span>|<span data-ttu-id="ee79c-119">説明</span><span class="sxs-lookup"><span data-stu-id="ee79c-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ee79c-120">アクティビティ</span><span class="sxs-lookup"><span data-stu-id="ee79c-120">Activity</span></span>|<span data-ttu-id="ee79c-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="ee79c-121">xs:string</span></span>|<span data-ttu-id="ee79c-122">アクティビティの型名。</span><span class="sxs-lookup"><span data-stu-id="ee79c-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="ee79c-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="ee79c-123">DisplayName</span></span>|<span data-ttu-id="ee79c-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="ee79c-124">xs:string</span></span>|<span data-ttu-id="ee79c-125">アクティビティの表示名。</span><span class="sxs-lookup"><span data-stu-id="ee79c-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="ee79c-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="ee79c-126">InstanceId</span></span>|<span data-ttu-id="ee79c-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="ee79c-127">xs:string</span></span>|<span data-ttu-id="ee79c-128">アクティビティのインスタンス ID。</span><span class="sxs-lookup"><span data-stu-id="ee79c-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="ee79c-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ee79c-129">AppDomain</span></span>|<span data-ttu-id="ee79c-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="ee79c-130">xs:string</span></span>|<span data-ttu-id="ee79c-131">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="ee79c-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
