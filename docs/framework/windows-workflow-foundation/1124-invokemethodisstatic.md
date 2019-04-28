---
title: 1124 - InvokeMethodIsStatic
ms.date: 03/30/2017
ms.assetid: b9643641-fb52-4fa8-b354-4dd6617d68f6
ms.openlocfilehash: 49a9dec73392681fd4150c611f78399a1e15dd48
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924060"
---
# <a name="1124---invokemethodisstatic"></a><span data-ttu-id="6daaa-102">1124 - InvokeMethodIsStatic</span><span class="sxs-lookup"><span data-stu-id="6daaa-102">1124 - InvokeMethodIsStatic</span></span>
## <a name="properties"></a><span data-ttu-id="6daaa-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="6daaa-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6daaa-104">ID</span><span class="sxs-lookup"><span data-stu-id="6daaa-104">ID</span></span>|<span data-ttu-id="6daaa-105">1124</span><span class="sxs-lookup"><span data-stu-id="6daaa-105">1124</span></span>|  
|<span data-ttu-id="6daaa-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="6daaa-106">Keywords</span></span>|<span data-ttu-id="6daaa-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="6daaa-107">WFRuntime</span></span>|  
|<span data-ttu-id="6daaa-108">レベル</span><span class="sxs-lookup"><span data-stu-id="6daaa-108">Level</span></span>|<span data-ttu-id="6daaa-109">情報</span><span class="sxs-lookup"><span data-stu-id="6daaa-109">Information</span></span>|  
|<span data-ttu-id="6daaa-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="6daaa-110">Channel</span></span>|<span data-ttu-id="6daaa-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="6daaa-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="6daaa-112">説明</span><span class="sxs-lookup"><span data-stu-id="6daaa-112">Description</span></span>  
 <span data-ttu-id="6daaa-113">CacheMetadata の手順では、InvokeMethod アクティビティは、呼び出すメソッドが静的であることを示します。</span><span class="sxs-lookup"><span data-stu-id="6daaa-113">During CacheMetadata step, InvokeMethod activity indicates the method to be invoked is static.</span></span>  
  
## <a name="message"></a><span data-ttu-id="6daaa-114">メッセージ</span><span class="sxs-lookup"><span data-stu-id="6daaa-114">Message</span></span>  
 <span data-ttu-id="6daaa-115">InvokeMethod '%1' - メソッドは Static です。</span><span class="sxs-lookup"><span data-stu-id="6daaa-115">InvokeMethod '%1' - method is Static.</span></span>  
  
## <a name="details"></a><span data-ttu-id="6daaa-116">説明</span><span class="sxs-lookup"><span data-stu-id="6daaa-116">Details</span></span>  
  
|<span data-ttu-id="6daaa-117">データ項目名</span><span class="sxs-lookup"><span data-stu-id="6daaa-117">Data Item Name</span></span>|<span data-ttu-id="6daaa-118">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="6daaa-118">Data Item Type</span></span>|<span data-ttu-id="6daaa-119">説明</span><span class="sxs-lookup"><span data-stu-id="6daaa-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="6daaa-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="6daaa-120">InvokeMethod</span></span>|<span data-ttu-id="6daaa-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="6daaa-121">xs:string</span></span>|<span data-ttu-id="6daaa-122">InvokeMethod アクティビティの表示名。</span><span class="sxs-lookup"><span data-stu-id="6daaa-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="6daaa-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="6daaa-123">AppDomain</span></span>|<span data-ttu-id="6daaa-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="6daaa-124">xs:string</span></span>|<span data-ttu-id="6daaa-125">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="6daaa-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
