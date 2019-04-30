---
title: 3507 - ServiceEndpointAdded
ms.date: 03/30/2017
ms.assetid: c068fc0e-07ee-4551-9824-ea7216e1fe37
ms.openlocfilehash: c787a1a5af752a3d08e2049cfa0b600b7739e56c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62009839"
---
# <a name="3507---serviceendpointadded"></a><span data-ttu-id="2fdcb-102">3507 - ServiceEndpointAdded</span><span class="sxs-lookup"><span data-stu-id="2fdcb-102">3507 - ServiceEndpointAdded</span></span>
## <a name="properties"></a><span data-ttu-id="2fdcb-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="2fdcb-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2fdcb-104">ID</span><span class="sxs-lookup"><span data-stu-id="2fdcb-104">ID</span></span>|<span data-ttu-id="2fdcb-105">3507</span><span class="sxs-lookup"><span data-stu-id="2fdcb-105">3507</span></span>|  
|<span data-ttu-id="2fdcb-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="2fdcb-106">Keywords</span></span>|<span data-ttu-id="2fdcb-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="2fdcb-107">WFServices</span></span>|  
|<span data-ttu-id="2fdcb-108">レベル</span><span class="sxs-lookup"><span data-stu-id="2fdcb-108">Level</span></span>|<span data-ttu-id="2fdcb-109">情報</span><span class="sxs-lookup"><span data-stu-id="2fdcb-109">Information</span></span>|  
|<span data-ttu-id="2fdcb-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="2fdcb-110">Channel</span></span>|<span data-ttu-id="2fdcb-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="2fdcb-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2fdcb-112">説明</span><span class="sxs-lookup"><span data-stu-id="2fdcb-112">Description</span></span>  
 <span data-ttu-id="2fdcb-113">サービス エンドポイントが追加されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="2fdcb-113">Indicates a service endpoint has been added.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2fdcb-114">メッセージ</span><span class="sxs-lookup"><span data-stu-id="2fdcb-114">Message</span></span>  
 <span data-ttu-id="2fdcb-115">アドレス '%1'、バインド '%2'、コントラクト '%3' のサービス エンドポイントが追加されました。</span><span class="sxs-lookup"><span data-stu-id="2fdcb-115">A service endpoint has been added for address '%1', binding '%2', and contract '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2fdcb-116">説明</span><span class="sxs-lookup"><span data-stu-id="2fdcb-116">Details</span></span>  
  
|<span data-ttu-id="2fdcb-117">データ項目名</span><span class="sxs-lookup"><span data-stu-id="2fdcb-117">Data Item Name</span></span>|<span data-ttu-id="2fdcb-118">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="2fdcb-118">Data Item Type</span></span>|<span data-ttu-id="2fdcb-119">説明</span><span class="sxs-lookup"><span data-stu-id="2fdcb-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2fdcb-120">Address</span><span class="sxs-lookup"><span data-stu-id="2fdcb-120">Address</span></span>|<span data-ttu-id="2fdcb-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="2fdcb-121">xs:string</span></span>|<span data-ttu-id="2fdcb-122">エンドポイントのアドレス。</span><span class="sxs-lookup"><span data-stu-id="2fdcb-122">The address of the endpoint.</span></span>|  
|<span data-ttu-id="2fdcb-123">バインディング</span><span class="sxs-lookup"><span data-stu-id="2fdcb-123">Binding</span></span>|<span data-ttu-id="2fdcb-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="2fdcb-124">xs:string</span></span>|<span data-ttu-id="2fdcb-125">エンドポイントのバインド。</span><span class="sxs-lookup"><span data-stu-id="2fdcb-125">The binding of the endpoint.</span></span>|  
|<span data-ttu-id="2fdcb-126">コントラクト</span><span class="sxs-lookup"><span data-stu-id="2fdcb-126">Contract</span></span>|<span data-ttu-id="2fdcb-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="2fdcb-127">xs:string</span></span>|<span data-ttu-id="2fdcb-128">エンドポイントのコントラクト。</span><span class="sxs-lookup"><span data-stu-id="2fdcb-128">The contract of the endpoint.</span></span>|  
|<span data-ttu-id="2fdcb-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="2fdcb-129">AppDomain</span></span>|<span data-ttu-id="2fdcb-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="2fdcb-130">xs:string</span></span>|<span data-ttu-id="2fdcb-131">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="2fdcb-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
