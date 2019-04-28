---
title: 4206 - UnlockInstanceException
ms.date: 03/30/2017
ms.assetid: 5a46dc5f-d517-4135-8905-25a42f01206b
ms.openlocfilehash: 3c981888b491f2797a431c2103ba3f5f0bd17046
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774323"
---
# <a name="4206---unlockinstanceexception"></a><span data-ttu-id="1f8c8-102">4206 - UnlockInstanceException</span><span class="sxs-lookup"><span data-stu-id="1f8c8-102">4206 - UnlockInstanceException</span></span>
## <a name="properties"></a><span data-ttu-id="1f8c8-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1f8c8-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1f8c8-104">ID</span><span class="sxs-lookup"><span data-stu-id="1f8c8-104">ID</span></span>|<span data-ttu-id="1f8c8-105">4206</span><span class="sxs-lookup"><span data-stu-id="1f8c8-105">4206</span></span>|  
|<span data-ttu-id="1f8c8-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="1f8c8-106">Keywords</span></span>|<span data-ttu-id="1f8c8-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="1f8c8-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="1f8c8-108">レベル</span><span class="sxs-lookup"><span data-stu-id="1f8c8-108">Level</span></span>|<span data-ttu-id="1f8c8-109">Error</span><span class="sxs-lookup"><span data-stu-id="1f8c8-109">Error</span></span>|  
|<span data-ttu-id="1f8c8-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="1f8c8-110">Channel</span></span>|<span data-ttu-id="1f8c8-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="1f8c8-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1f8c8-112">説明</span><span class="sxs-lookup"><span data-stu-id="1f8c8-112">Description</span></span>  
 <span data-ttu-id="1f8c8-113">インスタンスのロックを解除しようとしているときに例外が発生したことを示します。</span><span class="sxs-lookup"><span data-stu-id="1f8c8-113">Indicates an exception was encountered while trying to unlock an instance.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1f8c8-114">メッセージ</span><span class="sxs-lookup"><span data-stu-id="1f8c8-114">Message</span></span>  
 <span data-ttu-id="1f8c8-115">インスタンスのロックを解除しようとして、例外 %1 が発生しました。</span><span class="sxs-lookup"><span data-stu-id="1f8c8-115">Encountered exception %1 while attempting to unlock instance.</span></span>  
  
## <a name="details"></a><span data-ttu-id="1f8c8-116">説明</span><span class="sxs-lookup"><span data-stu-id="1f8c8-116">Details</span></span>  
  
|<span data-ttu-id="1f8c8-117">データ項目名</span><span class="sxs-lookup"><span data-stu-id="1f8c8-117">Data Item Name</span></span>|<span data-ttu-id="1f8c8-118">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="1f8c8-118">Data Item Type</span></span>|<span data-ttu-id="1f8c8-119">説明</span><span class="sxs-lookup"><span data-stu-id="1f8c8-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1f8c8-120">ExceptionMessage</span><span class="sxs-lookup"><span data-stu-id="1f8c8-120">ExceptionMessage</span></span>|<span data-ttu-id="1f8c8-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="1f8c8-121">xs:string</span></span>|<span data-ttu-id="1f8c8-122">SQL 例外からのメッセージ。</span><span class="sxs-lookup"><span data-stu-id="1f8c8-122">The message from the SQL exception.</span></span>|  
|<span data-ttu-id="1f8c8-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="1f8c8-123">AppDomain</span></span>|<span data-ttu-id="1f8c8-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="1f8c8-124">xs:string</span></span>|<span data-ttu-id="1f8c8-125">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="1f8c8-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
