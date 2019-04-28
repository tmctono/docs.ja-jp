---
title: 1041 - WorkflowApplicationPersistableIdle
ms.date: 03/30/2017
ms.assetid: 966adf2f-e21d-44df-a3ec-a8e285e0a316
ms.openlocfilehash: 07be0ae603443a1ef06cb539bba7b227d7b3e325
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924190"
---
# <a name="1041---workflowapplicationpersistableidle"></a><span data-ttu-id="34c2e-102">1041 - WorkflowApplicationPersistableIdle</span><span class="sxs-lookup"><span data-stu-id="34c2e-102">1041 - WorkflowApplicationPersistableIdle</span></span>
## <a name="properties"></a><span data-ttu-id="34c2e-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="34c2e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="34c2e-104">ID</span><span class="sxs-lookup"><span data-stu-id="34c2e-104">ID</span></span>|<span data-ttu-id="34c2e-105">1041</span><span class="sxs-lookup"><span data-stu-id="34c2e-105">1041</span></span>|  
|<span data-ttu-id="34c2e-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="34c2e-106">Keywords</span></span>|<span data-ttu-id="34c2e-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="34c2e-107">WFRuntime</span></span>|  
|<span data-ttu-id="34c2e-108">レベル</span><span class="sxs-lookup"><span data-stu-id="34c2e-108">Level</span></span>|<span data-ttu-id="34c2e-109">情報</span><span class="sxs-lookup"><span data-stu-id="34c2e-109">Information</span></span>|  
|<span data-ttu-id="34c2e-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="34c2e-110">Channel</span></span>|<span data-ttu-id="34c2e-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="34c2e-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="34c2e-112">説明</span><span class="sxs-lookup"><span data-stu-id="34c2e-112">Description</span></span>  
 <span data-ttu-id="34c2e-113">ワークフロー アプリケーションがアイドル状態のままであることを示します。</span><span class="sxs-lookup"><span data-stu-id="34c2e-113">Indicates that a workflow application is idle and persistable.</span></span> <span data-ttu-id="34c2e-114">ワークフロー アプリケーションはアイドル状態または永続化されます。</span><span class="sxs-lookup"><span data-stu-id="34c2e-114">The workflow application will be idled or persisted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="34c2e-115">メッセージ</span><span class="sxs-lookup"><span data-stu-id="34c2e-115">Message</span></span>  
 <span data-ttu-id="34c2e-116">WorkflowApplication Id: '%1' には、アイドル状態と永続化ができます。</span><span class="sxs-lookup"><span data-stu-id="34c2e-116">WorkflowApplication Id: '%1' is idle and persistable.</span></span>  <span data-ttu-id="34c2e-117">次の動作が行われます。 % 2。</span><span class="sxs-lookup"><span data-stu-id="34c2e-117">The following action will be taken: %2.</span></span>  
  
## <a name="details"></a><span data-ttu-id="34c2e-118">説明</span><span class="sxs-lookup"><span data-stu-id="34c2e-118">Details</span></span>  
  
|<span data-ttu-id="34c2e-119">データ項目名</span><span class="sxs-lookup"><span data-stu-id="34c2e-119">Data Item Name</span></span>|<span data-ttu-id="34c2e-120">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="34c2e-120">Data Item Type</span></span>|<span data-ttu-id="34c2e-121">説明</span><span class="sxs-lookup"><span data-stu-id="34c2e-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="34c2e-122">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="34c2e-122">WorkflowApplicationId</span></span>|<span data-ttu-id="34c2e-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="34c2e-123">xs:string</span></span>|<span data-ttu-id="34c2e-124">ワークフロー アプリケーション ID</span><span class="sxs-lookup"><span data-stu-id="34c2e-124">The workflow application id</span></span>|  
|<span data-ttu-id="34c2e-125">ActionTaken</span><span class="sxs-lookup"><span data-stu-id="34c2e-125">ActionTaken</span></span>|<span data-ttu-id="34c2e-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="34c2e-126">xs:string</span></span>|<span data-ttu-id="34c2e-127">ワークフロー アプリケーションで実行されるアクション。</span><span class="sxs-lookup"><span data-stu-id="34c2e-127">The action that will be taken on the workflow application.</span></span>|  
|<span data-ttu-id="34c2e-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="34c2e-128">AppDomain</span></span>|<span data-ttu-id="34c2e-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="34c2e-129">xs:string</span></span>|<span data-ttu-id="34c2e-130">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="34c2e-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
