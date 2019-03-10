---
title: WF 内のエラー処理アクティビティ
ms.date: 03/30/2017
ms.assetid: 24b68bd3-cef5-4413-ab82-2e2625f209aa
ms.openlocfilehash: 410c481745cc62a55a2b6e840d82b01fcc7f5766
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57707678"
---
# <a name="error-handling-activities-in-wf"></a><span data-ttu-id="f993a-102">WF 内のエラー処理アクティビティ</span><span class="sxs-lookup"><span data-stu-id="f993a-102">Error Handling Activities in WF</span></span>
[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] <span data-ttu-id="f993a-103">には、エラーの処理および回復を実装するためのシステム標準のアクティビティが用意されています。</span><span class="sxs-lookup"><span data-stu-id="f993a-103">provides several system-provided activities for implementing error handling and recovery.</span></span> <span data-ttu-id="f993a-104">詳細については、「 [例外](exceptions.md)で定義されているインターフェイスのプライベート C++ 固有の実装です。</span><span class="sxs-lookup"><span data-stu-id="f993a-104">For more information, see [Exceptions](exceptions.md).</span></span>  
  
## <a name="error-handling-activities"></a><span data-ttu-id="f993a-105">エラー処理アクティビティ</span><span class="sxs-lookup"><span data-stu-id="f993a-105">Error handling activities</span></span>  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.Rethrow>|<span data-ttu-id="f993a-106">`TryCatch` アクティビティ内からスローされた最後の例外を再スローします。</span><span class="sxs-lookup"><span data-stu-id="f993a-106">Rethrows the last exception thrown from within a `TryCatch` activity.</span></span>|  
|<xref:System.Activities.Statements.Throw>|<span data-ttu-id="f993a-107">例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="f993a-107">Throws an exception.</span></span>|  
|<xref:System.Activities.Statements.TryCatch>|<span data-ttu-id="f993a-108">例外処理を実装します。</span><span class="sxs-lookup"><span data-stu-id="f993a-108">Implements exception handling.</span></span>|
