---
title: 1036 - RuntimeTransactionCompletionRequested
ms.date: 03/30/2017
ms.assetid: d36b9f44-7c0f-4083-9d3a-9034dd2b98de
ms.openlocfilehash: 649ba542a9ed2f330ac71e447602d637530dc601
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924840"
---
# <a name="1036---runtimetransactioncompletionrequested"></a><span data-ttu-id="af587-102">1036 - RuntimeTransactionCompletionRequested</span><span class="sxs-lookup"><span data-stu-id="af587-102">1036 - RuntimeTransactionCompletionRequested</span></span>
## <a name="properties"></a><span data-ttu-id="af587-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="af587-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="af587-104">ID</span><span class="sxs-lookup"><span data-stu-id="af587-104">ID</span></span>|<span data-ttu-id="af587-105">1036</span><span class="sxs-lookup"><span data-stu-id="af587-105">1036</span></span>|  
|<span data-ttu-id="af587-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="af587-106">Keywords</span></span>|<span data-ttu-id="af587-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="af587-107">WFRuntime</span></span>|  
|<span data-ttu-id="af587-108">レベル</span><span class="sxs-lookup"><span data-stu-id="af587-108">Level</span></span>|<span data-ttu-id="af587-109">詳細</span><span class="sxs-lookup"><span data-stu-id="af587-109">Verbose</span></span>|  
|<span data-ttu-id="af587-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="af587-110">Channel</span></span>|<span data-ttu-id="af587-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="af587-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="af587-112">説明</span><span class="sxs-lookup"><span data-stu-id="af587-112">Description</span></span>  
 <span data-ttu-id="af587-113">アクティビティがランタイムのトランザクションの完了をスケジュールしたことを示します。</span><span class="sxs-lookup"><span data-stu-id="af587-113">Indicates an activity has scheduled the completion of the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="af587-114">メッセージ</span><span class="sxs-lookup"><span data-stu-id="af587-114">Message</span></span>  
 <span data-ttu-id="af587-115">Activity '%1'、DisplayName: '%2'、InstanceId: '%3' はランタイム トランザクションの完了をスケジュールしました。</span><span class="sxs-lookup"><span data-stu-id="af587-115">Activity '%1', DisplayName: '%2', InstanceId: '%3' has scheduled completion of the runtime transaction.</span></span>  
  
## <a name="details"></a><span data-ttu-id="af587-116">説明</span><span class="sxs-lookup"><span data-stu-id="af587-116">Details</span></span>  
  
|<span data-ttu-id="af587-117">データ項目名</span><span class="sxs-lookup"><span data-stu-id="af587-117">Data Item Name</span></span>|<span data-ttu-id="af587-118">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="af587-118">Data Item Type</span></span>|<span data-ttu-id="af587-119">説明</span><span class="sxs-lookup"><span data-stu-id="af587-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="af587-120">アクティビティ</span><span class="sxs-lookup"><span data-stu-id="af587-120">Activity</span></span>|<span data-ttu-id="af587-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="af587-121">xs:string</span></span>|<span data-ttu-id="af587-122">アクティビティの型名。</span><span class="sxs-lookup"><span data-stu-id="af587-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="af587-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="af587-123">DisplayName</span></span>|<span data-ttu-id="af587-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="af587-124">xs:string</span></span>|<span data-ttu-id="af587-125">アクティビティの表示名。</span><span class="sxs-lookup"><span data-stu-id="af587-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="af587-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="af587-126">InstanceId</span></span>|<span data-ttu-id="af587-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="af587-127">xs:string</span></span>|<span data-ttu-id="af587-128">アクティビティのインスタンス ID。</span><span class="sxs-lookup"><span data-stu-id="af587-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="af587-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="af587-129">AppDomain</span></span>|<span data-ttu-id="af587-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="af587-130">xs:string</span></span>|<span data-ttu-id="af587-131">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="af587-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
