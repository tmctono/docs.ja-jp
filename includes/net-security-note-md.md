---
ms.openlocfilehash: f01d0a24202ecda7e23cbe925bb6dc8962cb7574
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61750726"
---
> [!CAUTION]
>  <span data-ttu-id="a153d-101">コード アクセス セキュリティと部分的に信頼できるコード</span><span class="sxs-lookup"><span data-stu-id="a153d-101">Code Access Security and Partially Trusted Code</span></span>  
>   
>  <span data-ttu-id="a153d-102">.NET Framework には、コード アクセス セキュリティ (CAS) と呼ばれる、同一アプリケーションで実行される各種コードにさまざまな信頼レベルを強制的に適用するメカニズムが備わっています。</span><span class="sxs-lookup"><span data-stu-id="a153d-102">The .NET Framework provides a mechanism for the enforcement of varying levels of trust on different code running in the same application called Code Access Security (CAS).</span></span>  <span data-ttu-id="a153d-103">.NET Framework のコード アクセス セキュリティは、コードの実行元や他の ID 情報に基づいてセキュリティ境界を適用するメカニズムとして使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="a153d-103">Code Access Security in .NET Framework should not  be used as a mechanism for enforcing security boundaries based on code origination or other identity aspects.</span></span> <span data-ttu-id="a153d-104">現在、部分的に信頼されるコード (特に実行元が不明なコード) では、コード アクセス セキュリティと透過的セキュリティ コードがセキュリティ境界としてサポートされないように、ガイダンスを更新しています。</span><span class="sxs-lookup"><span data-stu-id="a153d-104">We are updating our guidance to reflect that Code Access Security and Security-Transparent Code will not be supported as a security boundary with partially trusted code, especially code of unknown origin.</span></span> <span data-ttu-id="a153d-105">発生元の不明なコードの読み込みと実行に関しては、他のセキュリティ対策を適切に導入することなく行わないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="a153d-105">We advise against loading and executing code of unknown origins without putting alternative security measures in place.</span></span>  
>   
>  <span data-ttu-id="a153d-106">このポリシーは .NET Framework のすべてのバージョンに適用されますが、Silverlight に含まれる .NET Framework には適用されません。</span><span class="sxs-lookup"><span data-stu-id="a153d-106">This policy applies to all versions of .NET Framework, but does not apply to the .NET Framework included in Silverlight.</span></span>