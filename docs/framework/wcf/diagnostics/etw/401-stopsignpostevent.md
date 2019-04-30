---
title: 401- StopSignPostEvent
ms.date: 03/30/2017
ms.assetid: e033d03a-510d-4300-aa65-ef02cb4807f2
ms.openlocfilehash: 1776252c362feb3c3ebc04651603944040ceee7b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61999753"
---
# <a name="401--stopsignpostevent"></a><span data-ttu-id="7e984-102">401- StopSignPostEvent</span><span class="sxs-lookup"><span data-stu-id="7e984-102">401- StopSignPostEvent</span></span>
## <a name="properties"></a><span data-ttu-id="7e984-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="7e984-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7e984-104">ID</span><span class="sxs-lookup"><span data-stu-id="7e984-104">ID</span></span>|<span data-ttu-id="7e984-105">401</span><span class="sxs-lookup"><span data-stu-id="7e984-105">401</span></span>|  
|<span data-ttu-id="7e984-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="7e984-106">Keywords</span></span>|<span data-ttu-id="7e984-107">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="7e984-107">Troubleshooting</span></span>|  
|<span data-ttu-id="7e984-108">レベル</span><span class="sxs-lookup"><span data-stu-id="7e984-108">Level</span></span>|<span data-ttu-id="7e984-109">情報</span><span class="sxs-lookup"><span data-stu-id="7e984-109">Information</span></span>|  
|<span data-ttu-id="7e984-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="7e984-110">Channel</span></span>|<span data-ttu-id="7e984-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="7e984-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="7e984-112">説明</span><span class="sxs-lookup"><span data-stu-id="7e984-112">Description</span></span>  
 <span data-ttu-id="7e984-113">このイベントは、エンド ツー エンド アクティビティの終了を示します。</span><span class="sxs-lookup"><span data-stu-id="7e984-113">This event marks the end of an end-to-end activity.</span></span> <span data-ttu-id="7e984-114">ここにはアクティビティの名前が指定されています。</span><span class="sxs-lookup"><span data-stu-id="7e984-114">It contains the name of the activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="7e984-115">メッセージ</span><span class="sxs-lookup"><span data-stu-id="7e984-115">Message</span></span>  
 <span data-ttu-id="7e984-116">アクティビティの境界</span><span class="sxs-lookup"><span data-stu-id="7e984-116">Activity boundary.</span></span>  
  
## <a name="details"></a><span data-ttu-id="7e984-117">説明</span><span class="sxs-lookup"><span data-stu-id="7e984-117">Details</span></span>  
  
|<span data-ttu-id="7e984-118">データ項目名</span><span class="sxs-lookup"><span data-stu-id="7e984-118">Data Item Name</span></span>|<span data-ttu-id="7e984-119">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="7e984-119">Data Item Type</span></span>|<span data-ttu-id="7e984-120">説明</span><span class="sxs-lookup"><span data-stu-id="7e984-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="7e984-121">Extended Data</span><span class="sxs-lookup"><span data-stu-id="7e984-121">Extended Data</span></span>|`xs:string`|<span data-ttu-id="7e984-122">アクティビティの名前。</span><span class="sxs-lookup"><span data-stu-id="7e984-122">The name of the activity.</span></span>|  
|<span data-ttu-id="7e984-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="7e984-123">AppDomain</span></span>|`xs:string`|<span data-ttu-id="7e984-124">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="7e984-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
