---
title: 1005 - WorkflowApplicationIdled
ms.date: 03/30/2017
ms.assetid: 74d77dfa-f20d-4fe9-a6ae-e6d1b5fe4182
ms.openlocfilehash: 6bbd12e8025b6a127dbfec8e5d3690825c188c4d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008604"
---
# <a name="1005---workflowapplicationidled"></a><span data-ttu-id="19f4d-102">1005 - WorkflowApplicationIdled</span><span class="sxs-lookup"><span data-stu-id="19f4d-102">1005 - WorkflowApplicationIdled</span></span>
## <a name="properties"></a><span data-ttu-id="19f4d-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="19f4d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="19f4d-104">ID</span><span class="sxs-lookup"><span data-stu-id="19f4d-104">ID</span></span>|<span data-ttu-id="19f4d-105">1005</span><span class="sxs-lookup"><span data-stu-id="19f4d-105">1005</span></span>|  
|<span data-ttu-id="19f4d-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="19f4d-106">Keywords</span></span>|<span data-ttu-id="19f4d-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="19f4d-107">WFRuntime</span></span>|  
|<span data-ttu-id="19f4d-108">レベル</span><span class="sxs-lookup"><span data-stu-id="19f4d-108">Level</span></span>|<span data-ttu-id="19f4d-109">情報</span><span class="sxs-lookup"><span data-stu-id="19f4d-109">Information</span></span>|  
|<span data-ttu-id="19f4d-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="19f4d-110">Channel</span></span>|<span data-ttu-id="19f4d-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="19f4d-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="19f4d-112">説明</span><span class="sxs-lookup"><span data-stu-id="19f4d-112">Description</span></span>  
 <span data-ttu-id="19f4d-113">ワークフロー アプリケーションがアイドル状態になったことを示します。</span><span class="sxs-lookup"><span data-stu-id="19f4d-113">Indicates a workflow application has idled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="19f4d-114">メッセージ</span><span class="sxs-lookup"><span data-stu-id="19f4d-114">Message</span></span>  
 <span data-ttu-id="19f4d-115">WorkflowApplication ID: '%1' がアイドル状態になりました。</span><span class="sxs-lookup"><span data-stu-id="19f4d-115">WorkflowApplication Id: '%1' went idle.</span></span>  
  
## <a name="details"></a><span data-ttu-id="19f4d-116">説明</span><span class="sxs-lookup"><span data-stu-id="19f4d-116">Details</span></span>  
  
|<span data-ttu-id="19f4d-117">データ項目名</span><span class="sxs-lookup"><span data-stu-id="19f4d-117">Data Item Name</span></span>|<span data-ttu-id="19f4d-118">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="19f4d-118">Data Item Type</span></span>|<span data-ttu-id="19f4d-119">説明</span><span class="sxs-lookup"><span data-stu-id="19f4d-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="19f4d-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="19f4d-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="19f4d-121">ワークフロー アプリケーション ID</span><span class="sxs-lookup"><span data-stu-id="19f4d-121">The workflow application id</span></span>|  
|<span data-ttu-id="19f4d-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="19f4d-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="19f4d-123">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="19f4d-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
