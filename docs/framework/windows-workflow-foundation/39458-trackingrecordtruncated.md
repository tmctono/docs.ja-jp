---
title: 39458 - TrackingRecordTruncated
ms.date: 03/30/2017
ms.assetid: 5352f0eb-d571-454a-bab5-e2162888b218
ms.openlocfilehash: 416feb4073b31178b016ae72c9cd85e15c4a68c3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774414"
---
# <a name="39458---trackingrecordtruncated"></a><span data-ttu-id="0d57b-102">39458 - TrackingRecordTruncated</span><span class="sxs-lookup"><span data-stu-id="0d57b-102">39458 - TrackingRecordTruncated</span></span>
## <a name="properties"></a><span data-ttu-id="0d57b-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="0d57b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0d57b-104">ID</span><span class="sxs-lookup"><span data-stu-id="0d57b-104">ID</span></span>|<span data-ttu-id="0d57b-105">39458</span><span class="sxs-lookup"><span data-stu-id="0d57b-105">39458</span></span>|  
|<span data-ttu-id="0d57b-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="0d57b-106">Keywords</span></span>|<span data-ttu-id="0d57b-107">WFTracking</span><span class="sxs-lookup"><span data-stu-id="0d57b-107">WFTracking</span></span>|  
|<span data-ttu-id="0d57b-108">レベル</span><span class="sxs-lookup"><span data-stu-id="0d57b-108">Level</span></span>|<span data-ttu-id="0d57b-109">警告</span><span class="sxs-lookup"><span data-stu-id="0d57b-109">Warning</span></span>|  
|<span data-ttu-id="0d57b-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="0d57b-110">Channel</span></span>|<span data-ttu-id="0d57b-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="0d57b-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0d57b-112">説明</span><span class="sxs-lookup"><span data-stu-id="0d57b-112">Description</span></span>  
 <span data-ttu-id="0d57b-113">追跡レコードが省略されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="0d57b-113">Indicates a tracking record has been truncated.</span></span> <span data-ttu-id="0d57b-114">変数、注釈、ユーザー データは削除されています。</span><span class="sxs-lookup"><span data-stu-id="0d57b-114">Variables/annotations/user data have been removed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0d57b-115">メッセージ</span><span class="sxs-lookup"><span data-stu-id="0d57b-115">Message</span></span>  
 <span data-ttu-id="0d57b-116">プロバイダー %2 の ETW セッションに書き込まれた追跡レコード %1 が切り捨てられました。</span><span class="sxs-lookup"><span data-stu-id="0d57b-116">Truncated tracking record %1 written to ETW session with provider %2.</span></span> <span data-ttu-id="0d57b-117">変数/注釈/ユーザー データは削除されました</span><span class="sxs-lookup"><span data-stu-id="0d57b-117">Variables/annotations/user data have been removed</span></span>  
  
## <a name="details"></a><span data-ttu-id="0d57b-118">説明</span><span class="sxs-lookup"><span data-stu-id="0d57b-118">Details</span></span>  
  
|<span data-ttu-id="0d57b-119">データ項目名</span><span class="sxs-lookup"><span data-stu-id="0d57b-119">Data Item Name</span></span>|<span data-ttu-id="0d57b-120">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="0d57b-120">Data Item Type</span></span>|<span data-ttu-id="0d57b-121">説明</span><span class="sxs-lookup"><span data-stu-id="0d57b-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0d57b-122">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="0d57b-122">RecordNumber</span></span>|<span data-ttu-id="0d57b-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="0d57b-123">xs:string</span></span>|<span data-ttu-id="0d57b-124">追跡レコード番号。</span><span class="sxs-lookup"><span data-stu-id="0d57b-124">The tracking record number.</span></span>|  
|<span data-ttu-id="0d57b-125">ProviderId</span><span class="sxs-lookup"><span data-stu-id="0d57b-125">ProviderId</span></span>|<span data-ttu-id="0d57b-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="0d57b-126">xs:string</span></span>|<span data-ttu-id="0d57b-127">ETW プロバイダー ID。</span><span class="sxs-lookup"><span data-stu-id="0d57b-127">The ETW provider id.</span></span>|  
|<span data-ttu-id="0d57b-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0d57b-128">AppDomain</span></span>|<span data-ttu-id="0d57b-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="0d57b-129">xs:string</span></span>|<span data-ttu-id="0d57b-130">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="0d57b-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
