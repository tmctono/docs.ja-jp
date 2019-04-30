---
title: 1018 - StartCancelActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 68b4fa1d-eee6-4a2a-8c16-7e9d89f08ab9
ms.openlocfilehash: 8d7045b0a7f31ecfd5dd90f319192bd202804353
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008864"
---
# <a name="1018---startcancelactivityworkitem"></a><span data-ttu-id="5bfc0-102">1018 - StartCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="5bfc0-102">1018 - StartCancelActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="5bfc0-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="5bfc0-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5bfc0-104">ID</span><span class="sxs-lookup"><span data-stu-id="5bfc0-104">ID</span></span>|<span data-ttu-id="5bfc0-105">1018</span><span class="sxs-lookup"><span data-stu-id="5bfc0-105">1018</span></span>|  
|<span data-ttu-id="5bfc0-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="5bfc0-106">Keywords</span></span>|<span data-ttu-id="5bfc0-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="5bfc0-107">WFRuntime</span></span>|  
|<span data-ttu-id="5bfc0-108">レベル</span><span class="sxs-lookup"><span data-stu-id="5bfc0-108">Level</span></span>|<span data-ttu-id="5bfc0-109">詳細</span><span class="sxs-lookup"><span data-stu-id="5bfc0-109">Verbose</span></span>|  
|<span data-ttu-id="5bfc0-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="5bfc0-110">Channel</span></span>|<span data-ttu-id="5bfc0-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="5bfc0-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5bfc0-112">説明</span><span class="sxs-lookup"><span data-stu-id="5bfc0-112">Description</span></span>  
 <span data-ttu-id="5bfc0-113">CancelActivityWorkItem が実行を開始していることを示します。</span><span class="sxs-lookup"><span data-stu-id="5bfc0-113">Indicates a CancelActivityWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5bfc0-114">メッセージ</span><span class="sxs-lookup"><span data-stu-id="5bfc0-114">Message</span></span>  
 <span data-ttu-id="5bfc0-115">Activity '%1'、DisplayName: '%2'、InstanceId: '%3' の CancelActivityWorkItem の実行を開始しています。</span><span class="sxs-lookup"><span data-stu-id="5bfc0-115">Starting execution of a CancelActivityWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5bfc0-116">説明</span><span class="sxs-lookup"><span data-stu-id="5bfc0-116">Details</span></span>  
  
|<span data-ttu-id="5bfc0-117">データ項目名</span><span class="sxs-lookup"><span data-stu-id="5bfc0-117">Data Item Name</span></span>|<span data-ttu-id="5bfc0-118">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="5bfc0-118">Data Item Type</span></span>|<span data-ttu-id="5bfc0-119">説明</span><span class="sxs-lookup"><span data-stu-id="5bfc0-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5bfc0-120">アクティビティ</span><span class="sxs-lookup"><span data-stu-id="5bfc0-120">Activity</span></span>|<span data-ttu-id="5bfc0-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="5bfc0-121">xs:string</span></span>|<span data-ttu-id="5bfc0-122">アクティビティの型名。</span><span class="sxs-lookup"><span data-stu-id="5bfc0-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="5bfc0-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="5bfc0-123">DisplayName</span></span>|<span data-ttu-id="5bfc0-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="5bfc0-124">xs:string</span></span>|<span data-ttu-id="5bfc0-125">アクティビティの表示名。</span><span class="sxs-lookup"><span data-stu-id="5bfc0-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="5bfc0-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="5bfc0-126">InstanceId</span></span>|<span data-ttu-id="5bfc0-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="5bfc0-127">xs:string</span></span>|<span data-ttu-id="5bfc0-128">アクティビティのインスタンス ID。</span><span class="sxs-lookup"><span data-stu-id="5bfc0-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="5bfc0-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="5bfc0-129">AppDomain</span></span>|<span data-ttu-id="5bfc0-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="5bfc0-130">xs:string</span></span>|<span data-ttu-id="5bfc0-131">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="5bfc0-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
