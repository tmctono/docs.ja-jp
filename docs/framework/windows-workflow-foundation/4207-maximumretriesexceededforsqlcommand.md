---
title: 4207 - MaximumRetriesExceededForSqlCommand
ms.date: 03/30/2017
ms.assetid: 8c8bee26-9ad4-4e01-bd16-0e1fd510fb6b
ms.openlocfilehash: b763e087d8ead2bcc0fadd1d0223ae1bd58c9fd9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774310"
---
# <a name="4207---maximumretriesexceededforsqlcommand"></a><span data-ttu-id="b9d62-102">4207 - MaximumRetriesExceededForSqlCommand</span><span class="sxs-lookup"><span data-stu-id="b9d62-102">4207 - MaximumRetriesExceededForSqlCommand</span></span>
## <a name="properties"></a><span data-ttu-id="b9d62-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="b9d62-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b9d62-104">ID</span><span class="sxs-lookup"><span data-stu-id="b9d62-104">ID</span></span>|<span data-ttu-id="b9d62-105">4207</span><span class="sxs-lookup"><span data-stu-id="b9d62-105">4207</span></span>|  
|<span data-ttu-id="b9d62-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="b9d62-106">Keywords</span></span>|<span data-ttu-id="b9d62-107">クオータ、WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="b9d62-107">Quota, WFInstanceStore</span></span>|  
|<span data-ttu-id="b9d62-108">レベル</span><span class="sxs-lookup"><span data-stu-id="b9d62-108">Level</span></span>|<span data-ttu-id="b9d62-109">情報</span><span class="sxs-lookup"><span data-stu-id="b9d62-109">Information</span></span>|  
|<span data-ttu-id="b9d62-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="b9d62-110">Channel</span></span>|<span data-ttu-id="b9d62-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="b9d62-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b9d62-112">説明</span><span class="sxs-lookup"><span data-stu-id="b9d62-112">Description</span></span>  
 <span data-ttu-id="b9d62-113">再試行が最大実行回数実行されたので、SQL プロバイダーは SQL コマンドの再試行を停止しようとしていることを示します。</span><span class="sxs-lookup"><span data-stu-id="b9d62-113">Indicates SQL provider is giving up retrying a SQL command as the maximum number of retries have been performed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b9d62-114">メッセージ</span><span class="sxs-lookup"><span data-stu-id="b9d62-114">Message</span></span>  
 <span data-ttu-id="b9d62-115">SQL コマンドが最大実行回数実行されたので、この SQL コマンドの再試行を停止します。</span><span class="sxs-lookup"><span data-stu-id="b9d62-115">Giving up retrying a SQL command as the maximum number of retries have been performed.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b9d62-116">説明</span><span class="sxs-lookup"><span data-stu-id="b9d62-116">Details</span></span>  
  
|<span data-ttu-id="b9d62-117">データ項目名</span><span class="sxs-lookup"><span data-stu-id="b9d62-117">Data Item Name</span></span>|<span data-ttu-id="b9d62-118">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="b9d62-118">Data Item Type</span></span>|<span data-ttu-id="b9d62-119">説明</span><span class="sxs-lookup"><span data-stu-id="b9d62-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b9d62-120">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b9d62-120">AppDomain</span></span>|<span data-ttu-id="b9d62-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="b9d62-121">xs:string</span></span>|<span data-ttu-id="b9d62-122">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="b9d62-122">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
