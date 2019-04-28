---
title: 1126 - InvokedMethodThrewException
ms.date: 03/30/2017
ms.assetid: 0d3cff1a-97e6-4b6c-be18-108c6881bfc0
ms.openlocfilehash: 714a98a300426d80c3b494d701ae1bd53a49592f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924008"
---
# <a name="1126---invokedmethodthrewexception"></a><span data-ttu-id="27570-102">1126 - InvokedMethodThrewException</span><span class="sxs-lookup"><span data-stu-id="27570-102">1126 - InvokedMethodThrewException</span></span>
## <a name="properties"></a><span data-ttu-id="27570-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="27570-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="27570-104">ID</span><span class="sxs-lookup"><span data-stu-id="27570-104">ID</span></span>|<span data-ttu-id="27570-105">1126</span><span class="sxs-lookup"><span data-stu-id="27570-105">1126</span></span>|  
|<span data-ttu-id="27570-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="27570-106">Keywords</span></span>|<span data-ttu-id="27570-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="27570-107">WFRuntime</span></span>|  
|<span data-ttu-id="27570-108">レベル</span><span class="sxs-lookup"><span data-stu-id="27570-108">Level</span></span>|<span data-ttu-id="27570-109">情報</span><span class="sxs-lookup"><span data-stu-id="27570-109">Information</span></span>|  
|<span data-ttu-id="27570-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="27570-110">Channel</span></span>|<span data-ttu-id="27570-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="27570-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="27570-112">説明</span><span class="sxs-lookup"><span data-stu-id="27570-112">Description</span></span>  
 <span data-ttu-id="27570-113">InvokeMethod アクティビティによって呼び出されたメソッドにより、例外がスローされたことを示します。</span><span class="sxs-lookup"><span data-stu-id="27570-113">Indicates an exception was thrown by the method called by the InvokeMethod activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="27570-114">メッセージ</span><span class="sxs-lookup"><span data-stu-id="27570-114">Message</span></span>  
 <span data-ttu-id="27570-115">アクティビティ '%1' によって呼び出されたメソッドで例外がスローされました。</span><span class="sxs-lookup"><span data-stu-id="27570-115">An exception was thrown in the method called by the activity '%1'.</span></span> <span data-ttu-id="27570-116">%2</span><span class="sxs-lookup"><span data-stu-id="27570-116">%2</span></span>  
  
## <a name="details"></a><span data-ttu-id="27570-117">説明</span><span class="sxs-lookup"><span data-stu-id="27570-117">Details</span></span>  
  
|<span data-ttu-id="27570-118">データ項目名</span><span class="sxs-lookup"><span data-stu-id="27570-118">Data Item Name</span></span>|<span data-ttu-id="27570-119">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="27570-119">Data Item Type</span></span>|<span data-ttu-id="27570-120">説明</span><span class="sxs-lookup"><span data-stu-id="27570-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="27570-121">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="27570-121">InvokeMethod</span></span>|<span data-ttu-id="27570-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="27570-122">xs:string</span></span>|<span data-ttu-id="27570-123">InvokeMethod アクティビティの表示名。</span><span class="sxs-lookup"><span data-stu-id="27570-123">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="27570-124">例外</span><span class="sxs-lookup"><span data-stu-id="27570-124">Exception</span></span>|<span data-ttu-id="27570-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="27570-125">xs:string</span></span>|<span data-ttu-id="27570-126">例外の詳細</span><span class="sxs-lookup"><span data-stu-id="27570-126">The exception details for the exception</span></span>|  
|<span data-ttu-id="27570-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="27570-127">AppDomain</span></span>|<span data-ttu-id="27570-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="27570-128">xs:string</span></span>|<span data-ttu-id="27570-129">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="27570-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
