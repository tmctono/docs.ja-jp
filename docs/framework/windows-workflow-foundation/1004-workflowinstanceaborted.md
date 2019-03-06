---
title: 1004 - WorkflowInstanceAborted
ms.date: 03/30/2017
ms.assetid: edb9ab8c-0b9a-488d-aa96-9c8c7984b53c
ms.openlocfilehash: d34f6f1ab6af8e06a0f28fb043faf9fe16a8b211
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485188"
---
# <a name="1004---workflowinstanceaborted"></a><span data-ttu-id="a8e6c-102">1004 - WorkflowInstanceAborted</span><span class="sxs-lookup"><span data-stu-id="a8e6c-102">1004 - WorkflowInstanceAborted</span></span>

## <a name="properties"></a><span data-ttu-id="a8e6c-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="a8e6c-103">Properties</span></span>

|||
|-|-|
|<span data-ttu-id="a8e6c-104">ID</span><span class="sxs-lookup"><span data-stu-id="a8e6c-104">ID</span></span>|<span data-ttu-id="a8e6c-105">1004</span><span class="sxs-lookup"><span data-stu-id="a8e6c-105">1004</span></span>|
|<span data-ttu-id="a8e6c-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="a8e6c-106">Keywords</span></span>|<span data-ttu-id="a8e6c-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="a8e6c-107">WFRuntime</span></span>|
|<span data-ttu-id="a8e6c-108">レベル</span><span class="sxs-lookup"><span data-stu-id="a8e6c-108">Level</span></span>|<span data-ttu-id="a8e6c-109">情報</span><span class="sxs-lookup"><span data-stu-id="a8e6c-109">Information</span></span>|
|<span data-ttu-id="a8e6c-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="a8e6c-110">Channel</span></span>|<span data-ttu-id="a8e6c-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="a8e6c-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|

## <a name="description"></a><span data-ttu-id="a8e6c-112">説明</span><span class="sxs-lookup"><span data-stu-id="a8e6c-112">Description</span></span>

<span data-ttu-id="a8e6c-113">例外で、ワークフロー インスタンスが中止を示します。</span><span class="sxs-lookup"><span data-stu-id="a8e6c-113">Indicates a workflow instance has aborted with an exception.</span></span>

## <a name="message"></a><span data-ttu-id="a8e6c-114">メッセージ</span><span class="sxs-lookup"><span data-stu-id="a8e6c-114">Message</span></span>

<span data-ttu-id="a8e6c-115">WorkflowInstance ID: '%1' は例外により中止されました。</span><span class="sxs-lookup"><span data-stu-id="a8e6c-115">WorkflowInstance Id: '%1' was aborted with an exception.</span></span>

## <a name="details"></a><span data-ttu-id="a8e6c-116">詳細</span><span class="sxs-lookup"><span data-stu-id="a8e6c-116">Details</span></span>

|<span data-ttu-id="a8e6c-117">データ項目名</span><span class="sxs-lookup"><span data-stu-id="a8e6c-117">Data Item Name</span></span>|<span data-ttu-id="a8e6c-118">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="a8e6c-118">Data Item Type</span></span>|<span data-ttu-id="a8e6c-119">説明</span><span class="sxs-lookup"><span data-stu-id="a8e6c-119">Description</span></span>|
|--------------------|--------------------|-----------------|
|<span data-ttu-id="a8e6c-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="a8e6c-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="a8e6c-121">ワークフローのインスタンス ID</span><span class="sxs-lookup"><span data-stu-id="a8e6c-121">The instance id for the workflow</span></span>|
|<span data-ttu-id="a8e6c-122">例外</span><span class="sxs-lookup"><span data-stu-id="a8e6c-122">Exception</span></span>|`xs:string`|<span data-ttu-id="a8e6c-123">例外の詳細</span><span class="sxs-lookup"><span data-stu-id="a8e6c-123">The exception details for the exception</span></span>|
|<span data-ttu-id="a8e6c-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a8e6c-124">AppDomain</span></span>|`xs:string`|<span data-ttu-id="a8e6c-125">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="a8e6c-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
