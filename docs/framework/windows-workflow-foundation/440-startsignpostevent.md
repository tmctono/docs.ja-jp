---
title: 440 - StartSignpostEvent1
ms.date: 03/30/2017
ms.assetid: 27b551b5-ae76-49f8-bab8-6300009eb4c1
ms.openlocfilehash: 4b2b6b0fa9df4725edd4929512eb1d7534d933b1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774170"
---
# <a name="440---startsignpostevent1"></a><span data-ttu-id="7d8a2-102">440 - StartSignpostEvent1</span><span class="sxs-lookup"><span data-stu-id="7d8a2-102">440 - StartSignpostEvent1</span></span>
## <a name="properties"></a><span data-ttu-id="7d8a2-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="7d8a2-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7d8a2-104">ID</span><span class="sxs-lookup"><span data-stu-id="7d8a2-104">ID</span></span>|<span data-ttu-id="7d8a2-105">440</span><span class="sxs-lookup"><span data-stu-id="7d8a2-105">440</span></span>|  
|<span data-ttu-id="7d8a2-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="7d8a2-106">Keywords</span></span>|<span data-ttu-id="7d8a2-107">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="7d8a2-107">Troubleshooting</span></span>|  
|<span data-ttu-id="7d8a2-108">レベル</span><span class="sxs-lookup"><span data-stu-id="7d8a2-108">Level</span></span>|<span data-ttu-id="7d8a2-109">情報</span><span class="sxs-lookup"><span data-stu-id="7d8a2-109">Information</span></span>|  
|<span data-ttu-id="7d8a2-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="7d8a2-110">Channel</span></span>|<span data-ttu-id="7d8a2-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="7d8a2-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="7d8a2-112">説明</span><span class="sxs-lookup"><span data-stu-id="7d8a2-112">Description</span></span>  
 <span data-ttu-id="7d8a2-113">アクティビティ トレースでは、送信または受信においてメッセージがアクティビティの境界を越え始めたことを示します。</span><span class="sxs-lookup"><span data-stu-id="7d8a2-113">In activity tracing, indicates a message has started crossing an activity boundary in send or receive.</span></span>  
  
## <a name="message"></a><span data-ttu-id="7d8a2-114">メッセージ</span><span class="sxs-lookup"><span data-stu-id="7d8a2-114">Message</span></span>  
 <span data-ttu-id="7d8a2-115">アクティビティの境界</span><span class="sxs-lookup"><span data-stu-id="7d8a2-115">Activity boundary.</span></span>  
  
## <a name="details"></a><span data-ttu-id="7d8a2-116">説明</span><span class="sxs-lookup"><span data-stu-id="7d8a2-116">Details</span></span>  
  
|<span data-ttu-id="7d8a2-117">データ項目名</span><span class="sxs-lookup"><span data-stu-id="7d8a2-117">Data Item Name</span></span>|<span data-ttu-id="7d8a2-118">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="7d8a2-118">Data Item Type</span></span>|<span data-ttu-id="7d8a2-119">説明</span><span class="sxs-lookup"><span data-stu-id="7d8a2-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="7d8a2-120">ExtendedData</span><span class="sxs-lookup"><span data-stu-id="7d8a2-120">ExtendedData</span></span>|`xs:string`|<span data-ttu-id="7d8a2-121">アクティビティの名前。</span><span class="sxs-lookup"><span data-stu-id="7d8a2-121">The name of the activity.</span></span>|  
|<span data-ttu-id="7d8a2-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="7d8a2-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="7d8a2-123">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="7d8a2-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
