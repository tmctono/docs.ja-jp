---
title: 3508 - TrackingProfileNotFound
ms.date: 03/30/2017
ms.assetid: 4cee3c4a-0490-4c94-aa19-ef7ce7287c02
ms.openlocfilehash: 94c7ce231df241778f7c6ec5fe5998eae364750d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61755572"
---
# <a name="3508---trackingprofilenotfound"></a><span data-ttu-id="aeccb-102">3508 - TrackingProfileNotFound</span><span class="sxs-lookup"><span data-stu-id="aeccb-102">3508 - TrackingProfileNotFound</span></span>
## <a name="properties"></a><span data-ttu-id="aeccb-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="aeccb-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="aeccb-104">ID</span><span class="sxs-lookup"><span data-stu-id="aeccb-104">ID</span></span>|<span data-ttu-id="aeccb-105">3508</span><span class="sxs-lookup"><span data-stu-id="aeccb-105">3508</span></span>|  
|<span data-ttu-id="aeccb-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="aeccb-106">Keywords</span></span>|<span data-ttu-id="aeccb-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="aeccb-107">WFServices</span></span>|  
|<span data-ttu-id="aeccb-108">レベル</span><span class="sxs-lookup"><span data-stu-id="aeccb-108">Level</span></span>|<span data-ttu-id="aeccb-109">詳細</span><span class="sxs-lookup"><span data-stu-id="aeccb-109">Verbose</span></span>|  
|<span data-ttu-id="aeccb-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="aeccb-110">Channel</span></span>|<span data-ttu-id="aeccb-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="aeccb-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="aeccb-112">説明</span><span class="sxs-lookup"><span data-stu-id="aeccb-112">Description</span></span>  
 <span data-ttu-id="aeccb-113">構成ファイル内に TrackingProfile がないか、または ActivityDefinitionId がプロファイルと一致していないことを示します。</span><span class="sxs-lookup"><span data-stu-id="aeccb-113">Indicates either a TrackingProfile is not found in the config file or the ActivityDefinitionId does not match the profile.</span></span>  
  
## <a name="message"></a><span data-ttu-id="aeccb-114">メッセージ</span><span class="sxs-lookup"><span data-stu-id="aeccb-114">Message</span></span>  
 <span data-ttu-id="aeccb-115">ActivityDefinitionId '%2' の TrackingProfile '%1' が見つかりません。</span><span class="sxs-lookup"><span data-stu-id="aeccb-115">TrackingProfile '%1' for the ActivityDefinitionId '%2' not found.</span></span> <span data-ttu-id="aeccb-116">config ファイルに TrackingProfile がないか、ActivityDefinitionId が一致しません。</span><span class="sxs-lookup"><span data-stu-id="aeccb-116">Either the TrackingProfile is not found in the config file or the ActivityDefinitionId does not match.</span></span>  
  
## <a name="details"></a><span data-ttu-id="aeccb-117">説明</span><span class="sxs-lookup"><span data-stu-id="aeccb-117">Details</span></span>  
  
|<span data-ttu-id="aeccb-118">データ項目名</span><span class="sxs-lookup"><span data-stu-id="aeccb-118">Data Item Name</span></span>|<span data-ttu-id="aeccb-119">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="aeccb-119">Data Item Type</span></span>|<span data-ttu-id="aeccb-120">説明</span><span class="sxs-lookup"><span data-stu-id="aeccb-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="aeccb-121">TrackingProfile</span><span class="sxs-lookup"><span data-stu-id="aeccb-121">TrackingProfile</span></span>|<span data-ttu-id="aeccb-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="aeccb-122">xs:string</span></span>|<span data-ttu-id="aeccb-123">追跡プロファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="aeccb-123">The name of the tracking profile.</span></span>|  
|<span data-ttu-id="aeccb-124">ActivityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="aeccb-124">ActivityDefinitionId</span></span>|<span data-ttu-id="aeccb-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="aeccb-125">xs:string</span></span>|<span data-ttu-id="aeccb-126">アクティビティ定義 ID。</span><span class="sxs-lookup"><span data-stu-id="aeccb-126">The activity definition id.</span></span>|  
|<span data-ttu-id="aeccb-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="aeccb-127">AppDomain</span></span>|<span data-ttu-id="aeccb-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="aeccb-128">xs:string</span></span>|<span data-ttu-id="aeccb-129">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="aeccb-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
