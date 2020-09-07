---
ms.openlocfilehash: b7b16e39fa5df9732fa769f2bcd3696dff3b2a49
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496159"
---
### <a name="rsacngverifyhash-now-returns-false-for-any-verification-failure"></a><span data-ttu-id="0ee85-101">RSACng.VerifyHash で検証が失敗した場合に False が返されるようになった</span><span class="sxs-lookup"><span data-stu-id="0ee85-101">RSACng.VerifyHash now returns False for any verification failure</span></span>

#### <a name="details"></a><span data-ttu-id="0ee85-102">説明</span><span class="sxs-lookup"><span data-stu-id="0ee85-102">Details</span></span>

<span data-ttu-id="0ee85-103">.NET Framework 4.6.2 以降では、署名自体の形式が正しくない場合、このメソッドでは **False** が返されます。</span><span class="sxs-lookup"><span data-stu-id="0ee85-103">Starting with the .NET Framework 4.6.2, this method returns **False** if the signature itself is badly formatted.</span></span> <span data-ttu-id="0ee85-104">今すぐ false を返しますの検証に失敗しました。 .NET Framework 4.6 および 4.6.1 では、メソッドによってスローされる、<xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName>署名自体が正しくフォーマットされている場合。</span><span class="sxs-lookup"><span data-stu-id="0ee85-104">It now returns false for any verification failure.In the .NET Framework 4.6 and 4.6.1, the method throws a <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName> if the signature itself is badly formatted.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="0ee85-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="0ee85-105">Suggestion</span></span>

<span data-ttu-id="0ee85-106">検証が失敗し、メソッドで **False** が返される場合は、代わりにその実行が <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName> の処理に依存するコードが実行される必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ee85-106">Any code whose execution depends on handling the <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName> should instead execute if validation fails and the method returns **False**.</span></span>

| <span data-ttu-id="0ee85-107">名前</span><span class="sxs-lookup"><span data-stu-id="0ee85-107">Name</span></span>    | <span data-ttu-id="0ee85-108">値</span><span class="sxs-lookup"><span data-stu-id="0ee85-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="0ee85-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="0ee85-109">Scope</span></span>   |<span data-ttu-id="0ee85-110">マイナー</span><span class="sxs-lookup"><span data-stu-id="0ee85-110">Minor</span></span>|
|<span data-ttu-id="0ee85-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="0ee85-111">Version</span></span>|<span data-ttu-id="0ee85-112">4.6.2</span><span class="sxs-lookup"><span data-stu-id="0ee85-112">4.6.2</span></span>|
|<span data-ttu-id="0ee85-113">種類</span><span class="sxs-lookup"><span data-stu-id="0ee85-113">Type</span></span>|<span data-ttu-id="0ee85-114">ランタイム</span><span class="sxs-lookup"><span data-stu-id="0ee85-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="0ee85-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="0ee85-115">Affected APIs</span></span>

- <xref:System.Security.Cryptography.RSACng.VerifyHash(System.Byte[],System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Security.Cryptography.RSACng.VerifyHash(System.Byte[],System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)`

-->
