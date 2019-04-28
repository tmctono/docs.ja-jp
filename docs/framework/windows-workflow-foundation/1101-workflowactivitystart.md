---
title: 1101 - WorkflowActivityStart
ms.date: 03/30/2017
ms.assetid: 831cd386-b9b5-47a9-9690-aff6292ff348
ms.openlocfilehash: 1e6db97284b7ca83d532166d96d7a42df0a51091
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924151"
---
# <a name="1101---workflowactivitystart"></a><span data-ttu-id="49fe5-102">1101 - WorkflowActivityStart</span><span class="sxs-lookup"><span data-stu-id="49fe5-102">1101 - WorkflowActivityStart</span></span>
## <a name="properties"></a><span data-ttu-id="49fe5-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="49fe5-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="49fe5-104">ID</span><span class="sxs-lookup"><span data-stu-id="49fe5-104">ID</span></span>|<span data-ttu-id="49fe5-105">1101</span><span class="sxs-lookup"><span data-stu-id="49fe5-105">1101</span></span>|  
|<span data-ttu-id="49fe5-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="49fe5-106">Keywords</span></span>|<span data-ttu-id="49fe5-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="49fe5-107">WFRuntime</span></span>|  
|<span data-ttu-id="49fe5-108">レベル</span><span class="sxs-lookup"><span data-stu-id="49fe5-108">Level</span></span>|<span data-ttu-id="49fe5-109">情報</span><span class="sxs-lookup"><span data-stu-id="49fe5-109">Information</span></span>|  
|<span data-ttu-id="49fe5-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="49fe5-110">Channel</span></span>|<span data-ttu-id="49fe5-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="49fe5-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="49fe5-112">説明</span><span class="sxs-lookup"><span data-stu-id="49fe5-112">Description</span></span>  
 <span data-ttu-id="49fe5-113">ワークフロー アクティビティが開始されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="49fe5-113">Indicates a workflow activity has started.</span></span>  
  
## <a name="message"></a><span data-ttu-id="49fe5-114">メッセージ</span><span class="sxs-lookup"><span data-stu-id="49fe5-114">Message</span></span>  
 <span data-ttu-id="49fe5-115">WorkflowInstance ID: '%1' E2E アクティビティ</span><span class="sxs-lookup"><span data-stu-id="49fe5-115">WorkflowInstance Id: '%1' E2E Activity</span></span>  
  
## <a name="details"></a><span data-ttu-id="49fe5-116">説明</span><span class="sxs-lookup"><span data-stu-id="49fe5-116">Details</span></span>  
  
|<span data-ttu-id="49fe5-117">データ項目名</span><span class="sxs-lookup"><span data-stu-id="49fe5-117">Data Item Name</span></span>|<span data-ttu-id="49fe5-118">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="49fe5-118">Data Item Type</span></span>|<span data-ttu-id="49fe5-119">説明</span><span class="sxs-lookup"><span data-stu-id="49fe5-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="49fe5-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="49fe5-120">WorkflowInstanceId</span></span>|<span data-ttu-id="49fe5-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="49fe5-121">xs:string</span></span>|<span data-ttu-id="49fe5-122">ワークフロー インスタンス ID。</span><span class="sxs-lookup"><span data-stu-id="49fe5-122">The workflow instance id.</span></span>|  
|<span data-ttu-id="49fe5-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="49fe5-123">AppDomain</span></span>|<span data-ttu-id="49fe5-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="49fe5-124">xs:string</span></span>|<span data-ttu-id="49fe5-125">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="49fe5-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
