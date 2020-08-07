---
ms.openlocfilehash: 8b0edd9a49ca431355ab4f57fa041c5d1756d7eb
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "87855668"
---
> [!CAUTION]
> <span data-ttu-id="ff931-101">コードアクセスセキュリティ (CAS) と部分信頼コード</span><span class="sxs-lookup"><span data-stu-id="ff931-101">Code Access Security (CAS) and Partially Trusted Code</span></span>
>
> <span data-ttu-id="ff931-102">.NET Framework には、コード アクセス セキュリティ (CAS) と呼ばれる、同一アプリケーションで実行される各種コードにさまざまな信頼レベルを強制的に適用するメカニズムが備わっています。</span><span class="sxs-lookup"><span data-stu-id="ff931-102">The .NET Framework provides a mechanism for the enforcement of varying levels of trust on different code running in the same application called Code Access Security (CAS).</span></span>
>
> <span data-ttu-id="ff931-103">**CAS は、.NET Core、.NET 5、またはそれ以降のバージョンではサポートされていません。CAS は、7.0 より後のバージョンの C# ではサポートされていません。**</span><span class="sxs-lookup"><span data-stu-id="ff931-103">**CAS is not supported in .NET Core, .NET 5, or later versions. CAS is not supported by versions of C# later than 7.0.**</span></span>
>
> <span data-ttu-id="ff931-104">.NET Framework の CA は、コードの作成やその他の id の側面に基づいてセキュリティ境界を適用するためのメカニズムとして使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="ff931-104">CAS in .NET Framework should not be used as a mechanism for enforcing security boundaries based on code origination or other identity aspects.</span></span> <span data-ttu-id="ff931-105">CA とセキュリティ透過的なコードは、部分的に信頼されたコード、特に不明なオリジンコードを含むセキュリティ境界としてはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="ff931-105">CAS and Security-Transparent Code are not supported as a security boundary with partially trusted code, especially code of unknown origin.</span></span> <span data-ttu-id="ff931-106">発生元の不明なコードの読み込みと実行に関しては、他のセキュリティ対策を適切に導入することなく行わないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="ff931-106">We advise against loading and executing code of unknown origins without putting alternative security measures in place.</span></span>
>
> <span data-ttu-id="ff931-107">このポリシーは .NET Framework のすべてのバージョンに適用されますが、Silverlight に含まれる .NET Framework には適用されません。</span><span class="sxs-lookup"><span data-stu-id="ff931-107">This policy applies to all versions of .NET Framework, but does not apply to the .NET Framework included in Silverlight.</span></span>
