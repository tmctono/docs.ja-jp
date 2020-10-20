---
ms.openlocfilehash: 3164233f1ac056de385faa119143d75d3c2dc50c
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2020
ms.locfileid: "92224354"
---
> [!CAUTION]
> <span data-ttu-id="5b925-101">コードアクセスセキュリティ (CAS) と部分信頼コード</span><span class="sxs-lookup"><span data-stu-id="5b925-101">Code Access Security (CAS) and Partially Trusted Code</span></span>
>
> <span data-ttu-id="5b925-102">.NET Framework には、コード アクセス セキュリティ (CAS) と呼ばれる、同一アプリケーションで実行される各種コードにさまざまな信頼レベルを強制的に適用するメカニズムが備わっています。</span><span class="sxs-lookup"><span data-stu-id="5b925-102">The .NET Framework provides a mechanism for the enforcement of varying levels of trust on different code running in the same application called Code Access Security (CAS).</span></span>
>
> <span data-ttu-id="5b925-103">**CAS は、.NET Core、.NET 5、またはそれ以降のバージョンではサポートされていません。CAS は、7.0 より後のバージョンの C# ではサポートされていません。**</span><span class="sxs-lookup"><span data-stu-id="5b925-103">**CAS is not supported in .NET Core, .NET 5, or later versions. CAS is not supported by versions of C# later than 7.0.**</span></span>
>
> <span data-ttu-id="5b925-104">.NET Framework の CA は、コードの作成やその他の id の側面に基づいてセキュリティ境界を適用するためのメカニズムとして使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="5b925-104">CAS in .NET Framework should not be used as a mechanism for enforcing security boundaries based on code origination or other identity aspects.</span></span> <span data-ttu-id="5b925-105">CA と Security-Transparent コードは、部分的に信頼されたコード、特に不明な配信元のコードを含むセキュリティ境界としてはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="5b925-105">CAS and Security-Transparent Code are not supported as a security boundary with partially trusted code, especially code of unknown origin.</span></span> <span data-ttu-id="5b925-106">発生元の不明なコードの読み込みと実行に関しては、他のセキュリティ対策を適切に導入することなく行わないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="5b925-106">We advise against loading and executing code of unknown origins without putting alternative security measures in place.</span></span> <span data-ttu-id="5b925-107">.NET Framework は、CA サンドボックスに対して検出される可能性がある昇格した特権の悪用に対して、セキュリティ更新プログラムを発行しません。</span><span class="sxs-lookup"><span data-stu-id="5b925-107">.NET Framework will not issue security patches for any elevation-of-privilege exploits that might be discovered against the CAS sandbox.</span></span>
>
> <span data-ttu-id="5b925-108">このポリシーは .NET Framework のすべてのバージョンに適用されますが、Silverlight に含まれる .NET Framework には適用されません。</span><span class="sxs-lookup"><span data-stu-id="5b925-108">This policy applies to all versions of .NET Framework, but does not apply to the .NET Framework included in Silverlight.</span></span>
