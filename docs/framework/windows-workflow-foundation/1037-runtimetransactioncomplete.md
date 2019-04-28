---
title: 1037 - RuntimeTransactionComplete
ms.date: 03/30/2017
ms.assetid: 2c8c31e0-42a9-4f46-865b-2da9ab16a0ba
ms.openlocfilehash: 7a94c917157904c5cb84105c41842657a534c973
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924294"
---
# <a name="1037---runtimetransactioncomplete"></a><span data-ttu-id="81b38-102">1037 - RuntimeTransactionComplete</span><span class="sxs-lookup"><span data-stu-id="81b38-102">1037 - RuntimeTransactionComplete</span></span>
## <a name="properties"></a><span data-ttu-id="81b38-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="81b38-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="81b38-104">ID</span><span class="sxs-lookup"><span data-stu-id="81b38-104">ID</span></span>|<span data-ttu-id="81b38-105">1037</span><span class="sxs-lookup"><span data-stu-id="81b38-105">1037</span></span>|  
|<span data-ttu-id="81b38-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="81b38-106">Keywords</span></span>|<span data-ttu-id="81b38-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="81b38-107">WFRuntime</span></span>|  
|<span data-ttu-id="81b38-108">レベル</span><span class="sxs-lookup"><span data-stu-id="81b38-108">Level</span></span>|<span data-ttu-id="81b38-109">詳細</span><span class="sxs-lookup"><span data-stu-id="81b38-109">Verbose</span></span>|  
|<span data-ttu-id="81b38-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="81b38-110">Channel</span></span>|<span data-ttu-id="81b38-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="81b38-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="81b38-112">説明</span><span class="sxs-lookup"><span data-stu-id="81b38-112">Description</span></span>  
 <span data-ttu-id="81b38-113">ランタイム トランザクションが完了したことを示します。</span><span class="sxs-lookup"><span data-stu-id="81b38-113">Indicates the runtime transaction has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="81b38-114">メッセージ</span><span class="sxs-lookup"><span data-stu-id="81b38-114">Message</span></span>  
 <span data-ttu-id="81b38-115">ランタイム トランザクションは '%1' の状態で完了しました。</span><span class="sxs-lookup"><span data-stu-id="81b38-115">The runtime transaction has completed with the state '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="81b38-116">説明</span><span class="sxs-lookup"><span data-stu-id="81b38-116">Details</span></span>  
  
|<span data-ttu-id="81b38-117">データ項目名</span><span class="sxs-lookup"><span data-stu-id="81b38-117">Data Item Name</span></span>|<span data-ttu-id="81b38-118">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="81b38-118">Data Item Type</span></span>|<span data-ttu-id="81b38-119">説明</span><span class="sxs-lookup"><span data-stu-id="81b38-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="81b38-120">状態</span><span class="sxs-lookup"><span data-stu-id="81b38-120">State</span></span>|<span data-ttu-id="81b38-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="81b38-121">xs:string</span></span>|<span data-ttu-id="81b38-122">トランザクションの状態。</span><span class="sxs-lookup"><span data-stu-id="81b38-122">The state of the transaction.</span></span>|  
|<span data-ttu-id="81b38-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="81b38-123">AppDomain</span></span>|<span data-ttu-id="81b38-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="81b38-124">xs:string</span></span>|<span data-ttu-id="81b38-125">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="81b38-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
