---
ms.openlocfilehash: b893966ceb65246ed6a7d214011b17ca14c50d5a
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85802853"
---

> [!WARNING]
> <span data-ttu-id="d1fc6-101"><xref:System.Text.RegularExpressions> を使用して信頼できない入力を処理するときは、タイムアウトを渡します。</span><span class="sxs-lookup"><span data-stu-id="d1fc6-101">When using <xref:System.Text.RegularExpressions> to process untrusted input, pass a timeout.</span></span> <span data-ttu-id="d1fc6-102">悪意のあるユーザーが `RegularExpressions` に入力を提供して、[サービス拒否攻撃](https://www.us-cert.gov/ncas/tips/ST04-015)を行う可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d1fc6-102">A malicious user can provide input to `RegularExpressions` causing a [Denial-of-Service attack](https://www.us-cert.gov/ncas/tips/ST04-015).</span></span> <span data-ttu-id="d1fc6-103">`RegularExpressions` を使用する ASP.NET Core フレームワーク API は、タイムアウトを渡します。</span><span class="sxs-lookup"><span data-stu-id="d1fc6-103">ASP.NET Core framework APIs that use `RegularExpressions` pass a timeout.</span></span>
