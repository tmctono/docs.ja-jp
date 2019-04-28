---
title: 3503 - DuplicateCorrelationQuery
ms.date: 03/30/2017
ms.assetid: b857f8e6-ce4d-4da4-bc9d-6cd63fa558a4
ms.openlocfilehash: 37a689b30b0bcab9124472deb98627afbe30dfee
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61755598"
---
# <a name="3503---duplicatecorrelationquery"></a><span data-ttu-id="1fb98-102">3503 - DuplicateCorrelationQuery</span><span class="sxs-lookup"><span data-stu-id="1fb98-102">3503 - DuplicateCorrelationQuery</span></span>
## <a name="properties"></a><span data-ttu-id="1fb98-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1fb98-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1fb98-104">ID</span><span class="sxs-lookup"><span data-stu-id="1fb98-104">ID</span></span>|<span data-ttu-id="1fb98-105">3503</span><span class="sxs-lookup"><span data-stu-id="1fb98-105">3503</span></span>|  
|<span data-ttu-id="1fb98-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="1fb98-106">Keywords</span></span>|<span data-ttu-id="1fb98-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="1fb98-107">WFServices</span></span>|  
|<span data-ttu-id="1fb98-108">レベル</span><span class="sxs-lookup"><span data-stu-id="1fb98-108">Level</span></span>|<span data-ttu-id="1fb98-109">警告</span><span class="sxs-lookup"><span data-stu-id="1fb98-109">Warning</span></span>|  
|<span data-ttu-id="1fb98-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="1fb98-110">Channel</span></span>|<span data-ttu-id="1fb98-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="1fb98-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1fb98-112">説明</span><span class="sxs-lookup"><span data-stu-id="1fb98-112">Description</span></span>  
 <span data-ttu-id="1fb98-113">重複する CorrelationQuery が見つかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="1fb98-113">Indicates a duplicate CorrelationQuery was found.</span></span> <span data-ttu-id="1fb98-114">相関の計算時には、重複するクエリは使用されません。</span><span class="sxs-lookup"><span data-stu-id="1fb98-114">The duplicate query will not be used when calculating correlation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1fb98-115">メッセージ</span><span class="sxs-lookup"><span data-stu-id="1fb98-115">Message</span></span>  
 <span data-ttu-id="1fb98-116">Where='%1' で重複する CorrelationQuery が見つかりました。</span><span class="sxs-lookup"><span data-stu-id="1fb98-116">A duplicate CorrelationQuery was found with Where='%1'.</span></span> <span data-ttu-id="1fb98-117">相関の計算時には、この重複するクエリは使用されません。</span><span class="sxs-lookup"><span data-stu-id="1fb98-117">This duplicate query will not be used when calculating correlation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="1fb98-118">説明</span><span class="sxs-lookup"><span data-stu-id="1fb98-118">Details</span></span>  
  
|<span data-ttu-id="1fb98-119">データ項目名</span><span class="sxs-lookup"><span data-stu-id="1fb98-119">Data Item Name</span></span>|<span data-ttu-id="1fb98-120">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="1fb98-120">Data Item Type</span></span>|<span data-ttu-id="1fb98-121">説明</span><span class="sxs-lookup"><span data-stu-id="1fb98-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1fb98-122">Where</span><span class="sxs-lookup"><span data-stu-id="1fb98-122">Where</span></span>|<span data-ttu-id="1fb98-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="1fb98-123">xs:string</span></span>|<span data-ttu-id="1fb98-124">関連付けクエリの Where 部分。</span><span class="sxs-lookup"><span data-stu-id="1fb98-124">The Where portion of the correlation query.</span></span>|  
|<span data-ttu-id="1fb98-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="1fb98-125">AppDomain</span></span>|<span data-ttu-id="1fb98-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="1fb98-126">xs:string</span></span>|<span data-ttu-id="1fb98-127">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="1fb98-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
