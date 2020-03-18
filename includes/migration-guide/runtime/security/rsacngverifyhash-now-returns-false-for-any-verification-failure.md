---
ms.openlocfilehash: fc315faef750d93d914104dd568078aa3fc430d4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "72887796"
---
### <a name="rsacngverifyhash-now-returns-false-for-any-verification-failure"></a><span data-ttu-id="743c1-101">RSACng.VerifyHash で検証が失敗した場合に False が返されるようになった</span><span class="sxs-lookup"><span data-stu-id="743c1-101">RSACng.VerifyHash now returns False for any verification failure</span></span>

|   |   |
|---|---|
|<span data-ttu-id="743c1-102">説明</span><span class="sxs-lookup"><span data-stu-id="743c1-102">Details</span></span>|<span data-ttu-id="743c1-103">.NET Framework 4.6.2 以降では、署名自体の形式が正しくない場合、このメソッドでは **False** が返されます。</span><span class="sxs-lookup"><span data-stu-id="743c1-103">Starting with the .NET Framework 4.6.2, this method returns **False** if the signature itself is badly formatted.</span></span> <span data-ttu-id="743c1-104">今すぐ false を返しますの検証に失敗しました。 .NET Framework 4.6 および 4.6.1 では、メソッドによってスローされる、<xref:System.Security.Cryptography.CryptographicException?displayProperty=name>署名自体が正しくフォーマットされている場合。</span><span class="sxs-lookup"><span data-stu-id="743c1-104">It now returns false for any verification failure.In the .NET Framework 4.6 and 4.6.1, the method throws a <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> if the signature itself is badly formatted.</span></span>|
|<span data-ttu-id="743c1-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="743c1-105">Suggestion</span></span>|<span data-ttu-id="743c1-106">検証が失敗し、メソッドで <xref:System.Security.Cryptography.CryptographicException?displayProperty=name>False**が返される場合は、代わりにその実行が** の処理に依存するコードが実行される必要があります。</span><span class="sxs-lookup"><span data-stu-id="743c1-106">Any code whose execution depends on handling the <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> should instead execute if validation fails and the method returns **False**.</span></span>|
|<span data-ttu-id="743c1-107">スコープ</span><span class="sxs-lookup"><span data-stu-id="743c1-107">Scope</span></span>|<span data-ttu-id="743c1-108">Minor</span><span class="sxs-lookup"><span data-stu-id="743c1-108">Minor</span></span>|
|<span data-ttu-id="743c1-109">バージョン</span><span class="sxs-lookup"><span data-stu-id="743c1-109">Version</span></span>|<span data-ttu-id="743c1-110">4.6.2</span><span class="sxs-lookup"><span data-stu-id="743c1-110">4.6.2</span></span>|
|<span data-ttu-id="743c1-111">[種類]</span><span class="sxs-lookup"><span data-stu-id="743c1-111">Type</span></span>|<span data-ttu-id="743c1-112">ランタイム</span><span class="sxs-lookup"><span data-stu-id="743c1-112">Runtime</span></span>|
|<span data-ttu-id="743c1-113">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="743c1-113">Affected APIs</span></span>|<ul><li><xref:System.Security.Cryptography.RSACng.VerifyHash(System.Byte[],System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)?displayProperty=nameWithType></li></ul>|
