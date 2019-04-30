---
title: 1001 - WorkflowApplicationCompleted
ms.date: 03/30/2017
ms.assetid: 7a2ab59a-cf66-437a-b01e-f8f7268a3f7a
ms.openlocfilehash: 430174b96a499fff7e0156327bb15e066ce2ca36
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008643"
---
# <a name="1001---workflowapplicationcompleted"></a><span data-ttu-id="739fe-102">1001 - WorkflowApplicationCompleted</span><span class="sxs-lookup"><span data-stu-id="739fe-102">1001 - WorkflowApplicationCompleted</span></span>
## <a name="properties"></a><span data-ttu-id="739fe-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="739fe-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="739fe-104">ID</span><span class="sxs-lookup"><span data-stu-id="739fe-104">ID</span></span>|<span data-ttu-id="739fe-105">1001</span><span class="sxs-lookup"><span data-stu-id="739fe-105">1001</span></span>|  
|<span data-ttu-id="739fe-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="739fe-106">Keywords</span></span>|<span data-ttu-id="739fe-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="739fe-107">WFRuntime</span></span>|  
|<span data-ttu-id="739fe-108">レベル</span><span class="sxs-lookup"><span data-stu-id="739fe-108">Level</span></span>|<span data-ttu-id="739fe-109">情報</span><span class="sxs-lookup"><span data-stu-id="739fe-109">Information</span></span>|  
|<span data-ttu-id="739fe-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="739fe-110">Channel</span></span>|<span data-ttu-id="739fe-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="739fe-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="739fe-112">説明</span><span class="sxs-lookup"><span data-stu-id="739fe-112">Description</span></span>  
 <span data-ttu-id="739fe-113">ワークフロー アプリケーションが Closed 状態で完了したことを示します。</span><span class="sxs-lookup"><span data-stu-id="739fe-113">Indicates a workflow application has completed in the Closed state.</span></span>  
  
## <a name="message"></a><span data-ttu-id="739fe-114">メッセージ</span><span class="sxs-lookup"><span data-stu-id="739fe-114">Message</span></span>  
 <span data-ttu-id="739fe-115">WorkflowInstance ID: %1 は Closed 状態で完了しました。</span><span class="sxs-lookup"><span data-stu-id="739fe-115">WorkflowInstance Id: '%1' has completed in the Closed state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="739fe-116">説明</span><span class="sxs-lookup"><span data-stu-id="739fe-116">Details</span></span>  
  
|<span data-ttu-id="739fe-117">データ項目名</span><span class="sxs-lookup"><span data-stu-id="739fe-117">Data Item Name</span></span>|<span data-ttu-id="739fe-118">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="739fe-118">Data Item Type</span></span>|<span data-ttu-id="739fe-119">説明</span><span class="sxs-lookup"><span data-stu-id="739fe-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="739fe-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="739fe-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="739fe-121">ワークフローのインスタンス ID</span><span class="sxs-lookup"><span data-stu-id="739fe-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="739fe-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="739fe-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="739fe-123">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="739fe-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
