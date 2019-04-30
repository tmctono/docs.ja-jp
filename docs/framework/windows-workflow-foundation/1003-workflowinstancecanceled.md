---
title: 1003 - WorkflowInstanceCanceled
ms.date: 03/30/2017
ms.assetid: 64754dc2-c160-4bf3-869a-13d56694e2dc
ms.openlocfilehash: c76a2dab6a95bda7f3969af07f814aba30071c7f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008630"
---
# <a name="1003---workflowinstancecanceled"></a><span data-ttu-id="2e061-102">1003 - WorkflowInstanceCanceled</span><span class="sxs-lookup"><span data-stu-id="2e061-102">1003 - WorkflowInstanceCanceled</span></span>
## <a name="properties"></a><span data-ttu-id="2e061-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="2e061-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2e061-104">ID</span><span class="sxs-lookup"><span data-stu-id="2e061-104">ID</span></span>|<span data-ttu-id="2e061-105">1003</span><span class="sxs-lookup"><span data-stu-id="2e061-105">1003</span></span>|  
|<span data-ttu-id="2e061-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="2e061-106">Keywords</span></span>|<span data-ttu-id="2e061-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="2e061-107">WFRuntime</span></span>|  
|<span data-ttu-id="2e061-108">レベル</span><span class="sxs-lookup"><span data-stu-id="2e061-108">Level</span></span>|<span data-ttu-id="2e061-109">情報</span><span class="sxs-lookup"><span data-stu-id="2e061-109">Information</span></span>|  
|<span data-ttu-id="2e061-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="2e061-110">Channel</span></span>|<span data-ttu-id="2e061-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="2e061-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2e061-112">説明</span><span class="sxs-lookup"><span data-stu-id="2e061-112">Description</span></span>  
 <span data-ttu-id="2e061-113">ワークフロー インスタンスが Canceled 状態で完了したことを示します。</span><span class="sxs-lookup"><span data-stu-id="2e061-113">Indicates a workflow instance has completed in the Canceled state.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2e061-114">メッセージ</span><span class="sxs-lookup"><span data-stu-id="2e061-114">Message</span></span>  
 <span data-ttu-id="2e061-115">WorkflowInstance ID: %1 は Canceled 状態で完了しました。</span><span class="sxs-lookup"><span data-stu-id="2e061-115">WorkflowInstance Id: '%1' has completed in the Canceled state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2e061-116">説明</span><span class="sxs-lookup"><span data-stu-id="2e061-116">Details</span></span>  
  
|<span data-ttu-id="2e061-117">データ項目名</span><span class="sxs-lookup"><span data-stu-id="2e061-117">Data Item Name</span></span>|<span data-ttu-id="2e061-118">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="2e061-118">Data Item Type</span></span>|<span data-ttu-id="2e061-119">説明</span><span class="sxs-lookup"><span data-stu-id="2e061-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2e061-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="2e061-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="2e061-121">ワークフローのインスタンス ID</span><span class="sxs-lookup"><span data-stu-id="2e061-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="2e061-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="2e061-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="2e061-123">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="2e061-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
