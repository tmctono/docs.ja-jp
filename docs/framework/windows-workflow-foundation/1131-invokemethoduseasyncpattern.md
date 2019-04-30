---
title: 1131 - InvokeMethodUseAsyncPattern
ms.date: 03/30/2017
ms.assetid: eca50fa7-5276-4759-ad1c-e490b9bd1f82
ms.openlocfilehash: 150973935d12455aa671043a619fbd6fd7e77425
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62009956"
---
# <a name="1131---invokemethoduseasyncpattern"></a><span data-ttu-id="a0d00-102">1131 - InvokeMethodUseAsyncPattern</span><span class="sxs-lookup"><span data-stu-id="a0d00-102">1131 - InvokeMethodUseAsyncPattern</span></span>
## <a name="properties"></a><span data-ttu-id="a0d00-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="a0d00-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a0d00-104">ID</span><span class="sxs-lookup"><span data-stu-id="a0d00-104">ID</span></span>|<span data-ttu-id="a0d00-105">1131</span><span class="sxs-lookup"><span data-stu-id="a0d00-105">1131</span></span>|  
|<span data-ttu-id="a0d00-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="a0d00-106">Keywords</span></span>|<span data-ttu-id="a0d00-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="a0d00-107">WFRuntime</span></span>|  
|<span data-ttu-id="a0d00-108">レベル</span><span class="sxs-lookup"><span data-stu-id="a0d00-108">Level</span></span>|<span data-ttu-id="a0d00-109">情報</span><span class="sxs-lookup"><span data-stu-id="a0d00-109">Information</span></span>|  
|<span data-ttu-id="a0d00-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="a0d00-110">Channel</span></span>|<span data-ttu-id="a0d00-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="a0d00-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a0d00-112">説明</span><span class="sxs-lookup"><span data-stu-id="a0d00-112">Description</span></span>  
 <span data-ttu-id="a0d00-113">CacheMetadata の手順では、InvokeMethod アクティビティはメソッドを呼び出すときの非同期パターンを使用していることを示します。</span><span class="sxs-lookup"><span data-stu-id="a0d00-113">During CacheMetadata step, InvokeMethod activity indicates that it is using the async pattern when invoking the method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a0d00-114">メッセージ</span><span class="sxs-lookup"><span data-stu-id="a0d00-114">Message</span></span>  
 <span data-ttu-id="a0d00-115">InvokeMethod '%1' - メソッドでは '%2' および '%3' の非同期パターンを使用します。</span><span class="sxs-lookup"><span data-stu-id="a0d00-115">InvokeMethod '%1' - method uses asynchronous pattern of '%2' and '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a0d00-116">説明</span><span class="sxs-lookup"><span data-stu-id="a0d00-116">Details</span></span>  
  
|<span data-ttu-id="a0d00-117">データ項目名</span><span class="sxs-lookup"><span data-stu-id="a0d00-117">Data Item Name</span></span>|<span data-ttu-id="a0d00-118">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="a0d00-118">Data Item Type</span></span>|<span data-ttu-id="a0d00-119">説明</span><span class="sxs-lookup"><span data-stu-id="a0d00-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a0d00-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="a0d00-120">InvokeMethod</span></span>|<span data-ttu-id="a0d00-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="a0d00-121">xs:string</span></span>|<span data-ttu-id="a0d00-122">InvokeMethod アクティビティの表示名。</span><span class="sxs-lookup"><span data-stu-id="a0d00-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="a0d00-123">BeginMethod</span><span class="sxs-lookup"><span data-stu-id="a0d00-123">BeginMethod</span></span>|<span data-ttu-id="a0d00-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="a0d00-124">xs:string</span></span>|<span data-ttu-id="a0d00-125">begin メソッドの名前。</span><span class="sxs-lookup"><span data-stu-id="a0d00-125">The name of the begin method.</span></span>|  
|<span data-ttu-id="a0d00-126">EndMethod</span><span class="sxs-lookup"><span data-stu-id="a0d00-126">EndMethod</span></span>|<span data-ttu-id="a0d00-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="a0d00-127">xs:string</span></span>|<span data-ttu-id="a0d00-128">end メソッドの名前。</span><span class="sxs-lookup"><span data-stu-id="a0d00-128">The name of the end method.</span></span>|  
|<span data-ttu-id="a0d00-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a0d00-129">AppDomain</span></span>|<span data-ttu-id="a0d00-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="a0d00-130">xs:string</span></span>|<span data-ttu-id="a0d00-131">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="a0d00-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
