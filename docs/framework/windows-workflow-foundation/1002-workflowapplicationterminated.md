---
title: 1002 - WorkflowApplicationTerminated
ms.date: 03/30/2017
ms.assetid: 4e8b111f-79dc-4898-bb4a-e9b36f69420f
ms.openlocfilehash: 01c9aba6e863e07a1a999a28fccefbab95a34d5b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008656"
---
# <a name="1002---workflowapplicationterminated"></a><span data-ttu-id="8c526-102">1002 - WorkflowApplicationTerminated</span><span class="sxs-lookup"><span data-stu-id="8c526-102">1002 - WorkflowApplicationTerminated</span></span>
## <a name="properties"></a><span data-ttu-id="8c526-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="8c526-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8c526-104">ID</span><span class="sxs-lookup"><span data-stu-id="8c526-104">ID</span></span>|<span data-ttu-id="8c526-105">1002</span><span class="sxs-lookup"><span data-stu-id="8c526-105">1002</span></span>|  
|<span data-ttu-id="8c526-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="8c526-106">Keywords</span></span>|<span data-ttu-id="8c526-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="8c526-107">WFRuntime</span></span>|  
|<span data-ttu-id="8c526-108">レベル</span><span class="sxs-lookup"><span data-stu-id="8c526-108">Level</span></span>|<span data-ttu-id="8c526-109">情報</span><span class="sxs-lookup"><span data-stu-id="8c526-109">Information</span></span>|  
|<span data-ttu-id="8c526-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="8c526-110">Channel</span></span>|<span data-ttu-id="8c526-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="8c526-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8c526-112">説明</span><span class="sxs-lookup"><span data-stu-id="8c526-112">Description</span></span>  
 <span data-ttu-id="8c526-113">例外が発生し、ワークフロー アプリケーションが Faulted 状態で終了したことを示します。</span><span class="sxs-lookup"><span data-stu-id="8c526-113">Indicates a workflow application has terminated in the Faulted state with an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8c526-114">メッセージ</span><span class="sxs-lookup"><span data-stu-id="8c526-114">Message</span></span>  
 <span data-ttu-id="8c526-115">WorkflowApplication ID: %1 は中止されました。</span><span class="sxs-lookup"><span data-stu-id="8c526-115">WorkflowApplication Id: '%1' was terminated.</span></span> <span data-ttu-id="8c526-116">例外により Faulted 状態で完了しました。</span><span class="sxs-lookup"><span data-stu-id="8c526-116">It has completed in the Faulted state with an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8c526-117">説明</span><span class="sxs-lookup"><span data-stu-id="8c526-117">Details</span></span>  
  
|<span data-ttu-id="8c526-118">データ項目名</span><span class="sxs-lookup"><span data-stu-id="8c526-118">Data Item Name</span></span>|<span data-ttu-id="8c526-119">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="8c526-119">Data Item Type</span></span>|<span data-ttu-id="8c526-120">説明</span><span class="sxs-lookup"><span data-stu-id="8c526-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8c526-121">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="8c526-121">WorkflowApplicationId</span></span>|`xs:string`|<span data-ttu-id="8c526-122">ワークフロー アプリケーション ID</span><span class="sxs-lookup"><span data-stu-id="8c526-122">The workflow application id</span></span>|  
|<span data-ttu-id="8c526-123">例外</span><span class="sxs-lookup"><span data-stu-id="8c526-123">Exception</span></span>|`xs:string`|<span data-ttu-id="8c526-124">例外の詳細</span><span class="sxs-lookup"><span data-stu-id="8c526-124">The exception details for the exception</span></span>|  
|<span data-ttu-id="8c526-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="8c526-125">AppDomain</span></span>|`xs:string`|<span data-ttu-id="8c526-126">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="8c526-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
