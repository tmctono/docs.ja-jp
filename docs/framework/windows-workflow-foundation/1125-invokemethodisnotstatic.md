---
title: 1125 - InvokeMethodIsNotStatic
ms.date: 03/30/2017
ms.assetid: ea2b3827-63da-497b-b2c3-d5cebefe57a1
ms.openlocfilehash: 692c5e56dac0a69ab5705acd284f048391145641
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924264"
---
# <a name="1125---invokemethodisnotstatic"></a><span data-ttu-id="ecc46-102">1125 - InvokeMethodIsNotStatic</span><span class="sxs-lookup"><span data-stu-id="ecc46-102">1125 - InvokeMethodIsNotStatic</span></span>
## <a name="properties"></a><span data-ttu-id="ecc46-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="ecc46-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ecc46-104">ID</span><span class="sxs-lookup"><span data-stu-id="ecc46-104">ID</span></span>|<span data-ttu-id="ecc46-105">1125</span><span class="sxs-lookup"><span data-stu-id="ecc46-105">1125</span></span>|  
|<span data-ttu-id="ecc46-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="ecc46-106">Keywords</span></span>|<span data-ttu-id="ecc46-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="ecc46-107">WFRuntime</span></span>|  
|<span data-ttu-id="ecc46-108">レベル</span><span class="sxs-lookup"><span data-stu-id="ecc46-108">Level</span></span>|<span data-ttu-id="ecc46-109">情報</span><span class="sxs-lookup"><span data-stu-id="ecc46-109">Information</span></span>|  
|<span data-ttu-id="ecc46-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="ecc46-110">Channel</span></span>|<span data-ttu-id="ecc46-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="ecc46-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ecc46-112">説明</span><span class="sxs-lookup"><span data-stu-id="ecc46-112">Description</span></span>  
 <span data-ttu-id="ecc46-113">CacheMetadata の手順では、InvokeMethod アクティビティは、呼び出すメソッドが静的ではないことを示します。</span><span class="sxs-lookup"><span data-stu-id="ecc46-113">During CacheMetadata step, InvokeMethod activity indicates the method to be invoked is not static.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ecc46-114">メッセージ</span><span class="sxs-lookup"><span data-stu-id="ecc46-114">Message</span></span>  
 <span data-ttu-id="ecc46-115">InvokeMethod '%1' - メソッドは Static ではありません。</span><span class="sxs-lookup"><span data-stu-id="ecc46-115">InvokeMethod '%1' - method is not Static.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ecc46-116">説明</span><span class="sxs-lookup"><span data-stu-id="ecc46-116">Details</span></span>  
  
|<span data-ttu-id="ecc46-117">データ項目名</span><span class="sxs-lookup"><span data-stu-id="ecc46-117">Data Item Name</span></span>|<span data-ttu-id="ecc46-118">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="ecc46-118">Data Item Type</span></span>|<span data-ttu-id="ecc46-119">説明</span><span class="sxs-lookup"><span data-stu-id="ecc46-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ecc46-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="ecc46-120">InvokeMethod</span></span>|<span data-ttu-id="ecc46-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="ecc46-121">xs:string</span></span>|<span data-ttu-id="ecc46-122">InvokeMethod アクティビティの表示名。</span><span class="sxs-lookup"><span data-stu-id="ecc46-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="ecc46-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ecc46-123">AppDomain</span></span>|<span data-ttu-id="ecc46-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="ecc46-124">xs:string</span></span>|<span data-ttu-id="ecc46-125">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="ecc46-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
