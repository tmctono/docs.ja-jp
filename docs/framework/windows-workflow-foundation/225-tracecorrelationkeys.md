---
title: 225 - TraceCorrelationKeys
ms.date: 03/30/2017
ms.assetid: d9083aaf-3816-4c1c-bae0-2d7f49628345
ms.openlocfilehash: 0bb54387dbd738a01225008edfc45ecb7297cd00
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61755663"
---
# <a name="225---tracecorrelationkeys"></a><span data-ttu-id="fd3df-102">225 - TraceCorrelationKeys</span><span class="sxs-lookup"><span data-stu-id="fd3df-102">225 - TraceCorrelationKeys</span></span>
## <a name="properties"></a><span data-ttu-id="fd3df-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="fd3df-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fd3df-104">ID</span><span class="sxs-lookup"><span data-stu-id="fd3df-104">ID</span></span>|<span data-ttu-id="fd3df-105">225</span><span class="sxs-lookup"><span data-stu-id="fd3df-105">225</span></span>|  
|<span data-ttu-id="fd3df-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="fd3df-106">Keywords</span></span>|<span data-ttu-id="fd3df-107">Troubleshooting、ServiceModel</span><span class="sxs-lookup"><span data-stu-id="fd3df-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="fd3df-108">レベル</span><span class="sxs-lookup"><span data-stu-id="fd3df-108">Level</span></span>|<span data-ttu-id="fd3df-109">情報</span><span class="sxs-lookup"><span data-stu-id="fd3df-109">Information</span></span>|  
|<span data-ttu-id="fd3df-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="fd3df-110">Channel</span></span>|<span data-ttu-id="fd3df-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="fd3df-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="fd3df-112">説明</span><span class="sxs-lookup"><span data-stu-id="fd3df-112">Description</span></span>  
 <span data-ttu-id="fd3df-113">このイベントは、ワークフロー サービスでコンテンツ ベースの相関関係が使用されるときに生成されます。</span><span class="sxs-lookup"><span data-stu-id="fd3df-113">This event is emitted when content-based correlation is used for a workflow service.</span></span> <span data-ttu-id="fd3df-114">これには、メッセージとインスタンスの相関関係を定義するために適用されている相関関係キーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="fd3df-114">It contains the correlation keys that are applied to correlate a message to an instance.</span></span>  
  
## <a name="message"></a><span data-ttu-id="fd3df-115">メッセージ</span><span class="sxs-lookup"><span data-stu-id="fd3df-115">Message</span></span>  
 <span data-ttu-id="fd3df-116">親スコープ '%3' の値 '%2' を使用して相関関係キー '%1' が計算されました。</span><span class="sxs-lookup"><span data-stu-id="fd3df-116">Calculated correlation key '%1' using values '%2' in parent scope '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="fd3df-117">説明</span><span class="sxs-lookup"><span data-stu-id="fd3df-117">Details</span></span>  
  
|<span data-ttu-id="fd3df-118">データ項目名</span><span class="sxs-lookup"><span data-stu-id="fd3df-118">Data Item Name</span></span>|<span data-ttu-id="fd3df-119">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="fd3df-119">Data Item Type</span></span>|<span data-ttu-id="fd3df-120">説明</span><span class="sxs-lookup"><span data-stu-id="fd3df-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="fd3df-121">Instance Key</span><span class="sxs-lookup"><span data-stu-id="fd3df-121">Instance Key</span></span>|`xs:GUID`|<span data-ttu-id="fd3df-122">相関関係値から生成されたキー。</span><span class="sxs-lookup"><span data-stu-id="fd3df-122">The key that was generated from the correlation values.</span></span>|  
|<span data-ttu-id="fd3df-123">値</span><span class="sxs-lookup"><span data-stu-id="fd3df-123">Values</span></span>|`xs:string`|<span data-ttu-id="fd3df-124">相関関係インスタンス キーの計算に使用された値。</span><span class="sxs-lookup"><span data-stu-id="fd3df-124">The values that were used to compute the correlation instance key.</span></span>|  
|<span data-ttu-id="fd3df-125">Parent Scope</span><span class="sxs-lookup"><span data-stu-id="fd3df-125">Parent Scope</span></span>|`xs:string`||  
|<span data-ttu-id="fd3df-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="fd3df-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="fd3df-127">Web ホスト サービスの場合は、このフィールドにより、サービスが Web 階層内で一意に識別されます。</span><span class="sxs-lookup"><span data-stu-id="fd3df-127">For Web hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="fd3df-128">その形式が定義されている ' Web サイト名アプリケーション仮想パス&#124;サービス仮想パス&#124;ServiceName'。</span><span class="sxs-lookup"><span data-stu-id="fd3df-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="fd3df-129">例:' 既定の Web サイト/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'。</span><span class="sxs-lookup"><span data-stu-id="fd3df-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="fd3df-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="fd3df-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="fd3df-131">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="fd3df-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
