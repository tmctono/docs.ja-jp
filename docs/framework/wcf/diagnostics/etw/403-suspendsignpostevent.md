---
title: 403 - SuspendSignpostEvent
ms.date: 03/30/2017
ms.assetid: fb2e6f29-e556-47b4-b4c1-acd6b8879702
ms.openlocfilehash: 727d164b9cd47657af0d7810103a766f33cb35de
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61758055"
---
# <a name="403---suspendsignpostevent"></a><span data-ttu-id="8a843-102">403 - SuspendSignpostEvent</span><span class="sxs-lookup"><span data-stu-id="8a843-102">403 - SuspendSignpostEvent</span></span>
## <a name="properties"></a><span data-ttu-id="8a843-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="8a843-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8a843-104">ID</span><span class="sxs-lookup"><span data-stu-id="8a843-104">ID</span></span>|<span data-ttu-id="8a843-105">403</span><span class="sxs-lookup"><span data-stu-id="8a843-105">403</span></span>|  
|<span data-ttu-id="8a843-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="8a843-106">Keywords</span></span>|<span data-ttu-id="8a843-107">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="8a843-107">Troubleshooting</span></span>|  
|<span data-ttu-id="8a843-108">レベル</span><span class="sxs-lookup"><span data-stu-id="8a843-108">Level</span></span>|<span data-ttu-id="8a843-109">情報</span><span class="sxs-lookup"><span data-stu-id="8a843-109">Information</span></span>|  
|<span data-ttu-id="8a843-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="8a843-110">Channel</span></span>|<span data-ttu-id="8a843-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="8a843-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8a843-112">説明</span><span class="sxs-lookup"><span data-stu-id="8a843-112">Description</span></span>  
 <span data-ttu-id="8a843-113">このイベントは、エンド ツー エンド アクティビティの中断を示します。</span><span class="sxs-lookup"><span data-stu-id="8a843-113">This event marks the suspension of an end-to-end activity.</span></span> <span data-ttu-id="8a843-114">ここにはアクティビティの名前が指定されています。</span><span class="sxs-lookup"><span data-stu-id="8a843-114">It contains the name of the activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8a843-115">メッセージ</span><span class="sxs-lookup"><span data-stu-id="8a843-115">Message</span></span>  
 <span data-ttu-id="8a843-116">アクティビティの境界</span><span class="sxs-lookup"><span data-stu-id="8a843-116">Activity boundary.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8a843-117">説明</span><span class="sxs-lookup"><span data-stu-id="8a843-117">Details</span></span>  
  
|<span data-ttu-id="8a843-118">データ項目名</span><span class="sxs-lookup"><span data-stu-id="8a843-118">Data Item Name</span></span>|<span data-ttu-id="8a843-119">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="8a843-119">Data Item Type</span></span>|<span data-ttu-id="8a843-120">説明</span><span class="sxs-lookup"><span data-stu-id="8a843-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8a843-121">Extended Data</span><span class="sxs-lookup"><span data-stu-id="8a843-121">Extended Data</span></span>|`xs:string`|<span data-ttu-id="8a843-122">アクティビティの名前。</span><span class="sxs-lookup"><span data-stu-id="8a843-122">The name of the activity.</span></span>|  
|<span data-ttu-id="8a843-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="8a843-123">AppDomain</span></span>|`xs:string`|<span data-ttu-id="8a843-124">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="8a843-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
