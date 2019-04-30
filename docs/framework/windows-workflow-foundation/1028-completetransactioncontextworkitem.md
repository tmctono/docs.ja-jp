---
title: 1028 - CompleteTransactionContextWorkItem
ms.date: 03/30/2017
ms.assetid: 95423f9d-d29a-460e-bcd8-096e80af5bd0
ms.openlocfilehash: 806a437822cef8802a2bef6a54f924f84c88ef60
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008812"
---
# <a name="1028---completetransactioncontextworkitem"></a><span data-ttu-id="38a19-102">1028 - CompleteTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="38a19-102">1028 - CompleteTransactionContextWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="38a19-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="38a19-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="38a19-104">ID</span><span class="sxs-lookup"><span data-stu-id="38a19-104">ID</span></span>|<span data-ttu-id="38a19-105">1028</span><span class="sxs-lookup"><span data-stu-id="38a19-105">1028</span></span>|  
|<span data-ttu-id="38a19-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="38a19-106">Keywords</span></span>|<span data-ttu-id="38a19-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="38a19-107">WFRuntime</span></span>|  
|<span data-ttu-id="38a19-108">レベル</span><span class="sxs-lookup"><span data-stu-id="38a19-108">Level</span></span>|<span data-ttu-id="38a19-109">詳細</span><span class="sxs-lookup"><span data-stu-id="38a19-109">Verbose</span></span>|  
|<span data-ttu-id="38a19-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="38a19-110">Channel</span></span>|<span data-ttu-id="38a19-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="38a19-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="38a19-112">説明</span><span class="sxs-lookup"><span data-stu-id="38a19-112">Description</span></span>  
 <span data-ttu-id="38a19-113">TransactionContextWorkItem が完了したことを示します。</span><span class="sxs-lookup"><span data-stu-id="38a19-113">Indicates a TransactionContextWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="38a19-114">メッセージ</span><span class="sxs-lookup"><span data-stu-id="38a19-114">Message</span></span>  
 <span data-ttu-id="38a19-115">Activity '%1'、DisplayName: '%2'、InstanceId: '%3' の TransactionContextWorkItem が完了しました。</span><span class="sxs-lookup"><span data-stu-id="38a19-115">A TransactionContextWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="38a19-116">説明</span><span class="sxs-lookup"><span data-stu-id="38a19-116">Details</span></span>  
  
|<span data-ttu-id="38a19-117">データ項目名</span><span class="sxs-lookup"><span data-stu-id="38a19-117">Data Item Name</span></span>|<span data-ttu-id="38a19-118">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="38a19-118">Data Item Type</span></span>|<span data-ttu-id="38a19-119">説明</span><span class="sxs-lookup"><span data-stu-id="38a19-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="38a19-120">アクティビティ</span><span class="sxs-lookup"><span data-stu-id="38a19-120">Activity</span></span>|<span data-ttu-id="38a19-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="38a19-121">xs:string</span></span>|<span data-ttu-id="38a19-122">アクティビティの型名。</span><span class="sxs-lookup"><span data-stu-id="38a19-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="38a19-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="38a19-123">DisplayName</span></span>|<span data-ttu-id="38a19-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="38a19-124">xs:string</span></span>|<span data-ttu-id="38a19-125">アクティビティの表示名。</span><span class="sxs-lookup"><span data-stu-id="38a19-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="38a19-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="38a19-126">InstanceId</span></span>|<span data-ttu-id="38a19-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="38a19-127">xs:string</span></span>|<span data-ttu-id="38a19-128">アクティビティのインスタンス ID。</span><span class="sxs-lookup"><span data-stu-id="38a19-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="38a19-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="38a19-129">AppDomain</span></span>|<span data-ttu-id="38a19-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="38a19-130">xs:string</span></span>|<span data-ttu-id="38a19-131">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="38a19-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
