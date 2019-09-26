---
ms.openlocfilehash: 07ab65de16b72bd0844a39e4b35235c5f043f3ec
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117199"
---
### <a name="minimum-size-for-rsaopenssl-key-generation-has-increased"></a><span data-ttu-id="09754-101">RSAOpenSsl キー生成の最小サイズが増加しました</span><span class="sxs-lookup"><span data-stu-id="09754-101">Minimum size for RSAOpenSsl key generation has increased</span></span>

<span data-ttu-id="09754-102">Linux で新しい RSA キーを生成する場合の最小サイズが、384 ビットから 512 ビットに増加しました。</span><span class="sxs-lookup"><span data-stu-id="09754-102">The minimum size for generating new RSA keys on Linux has increased from 384-bit to 512-bit.</span></span>

#### <a name="change-description"></a><span data-ttu-id="09754-103">変更の説明</span><span class="sxs-lookup"><span data-stu-id="09754-103">Change description</span></span>

<span data-ttu-id="09754-104">.NET Core 3.0 より、Linux の <System.Security.Cryptography.RSA.Create%2A?displayProperty=nameWithType>、<System.Security.Cryptography.RSAOpenSsl.%23ctor%2A?displayProperty=nameWithType>、および <System.Security.Cryptography.RSACryptoServicePlatform.%23ctor%2A?displayProperty=nameWithType> から RSA インスタンスの `LegalKeySizes` プロパティによって報告される最小の有効キー サイズが 384 から 512 に増加しました。</span><span class="sxs-lookup"><span data-stu-id="09754-104">Starting with .NET Core 3.0, the minimum legal key size reported by the `LegalKeySizes` property on RSA instances from <System.Security.Cryptography.RSA.Create%2A?displayProperty=nameWithType>, <System.Security.Cryptography.RSAOpenSsl.%23ctor%2A?displayProperty=nameWithType>, and <System.Security.Cryptography.RSACryptoServicePlatform.%23ctor%2A?displayProperty=nameWithType> on Linux has increased from 384 to 512.</span></span>

<span data-ttu-id="09754-105">その結果、.NET Core 2.2 以前のバージョンでは、`RSA.Create(384)` などのメソッドの呼び出しが成功しています。</span><span class="sxs-lookup"><span data-stu-id="09754-105">As a result, in .NET Core 2.2 and earlier versions, a method call such as `RSA.Create(384)` succeeds.</span></span> <span data-ttu-id="09754-106">.NET Core 3.0 以降のバージョンでは、メソッドの呼び出し `RSA.Create(384)` によって、サイズが小さすぎることを示す例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="09754-106">In .NET Core 3.0 and later versions, the method call `RSA.Create(384)` throws an exception indicating the size is too small.</span></span>

<span data-ttu-id="09754-107">この変更は、Linux で暗号化操作を実行する OpenSSL によって、バージョン 1.0.2 と 1.1.0 の間で最小値が増加したためです。</span><span class="sxs-lookup"><span data-stu-id="09754-107">This changes was made because OpenSSL, which performs the cryptographic operations on Linux, raised its minimum between versions 1.0.2 and 1.1.0.</span></span>  <span data-ttu-id="09754-108">.NET Core 3.0 では、OpenSSL 1.0.x よりも 1.1.x が優先され、報告される最小バージョンが引き上げられ、この新しい依存関係のより高い制限が反映されます。</span><span class="sxs-lookup"><span data-stu-id="09754-108">.NET Core 3.0 prefers OpenSSL 1.1.x to 1.0.x, and the minimum reported version was raised to reflect this new higher dependency limitation.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="09754-109">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="09754-109">Version introduced</span></span>

<span data-ttu-id="09754-110">3.0</span><span class="sxs-lookup"><span data-stu-id="09754-110">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="09754-111">推奨される操作</span><span class="sxs-lookup"><span data-stu-id="09754-111">Recommended action</span></span>

<span data-ttu-id="09754-112">影響を受ける API を呼び出す場合は、生成されるキーのサイズがプロバイダーの最小を下回らないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="09754-112">If you call any of the affected APIs, ensure that the size of any generated keys is not less than the provider minimum.</span></span>

> [!NOTE]
> <span data-ttu-id="09754-113">384 ビットの RSA は、既に安全ではないと見なされています (512 ビットの RSA も同様)。</span><span class="sxs-lookup"><span data-stu-id="09754-113">384-bit RSA is already considered insecure (as is 512-bit RSA).</span></span> <span data-ttu-id="09754-114">[NIST Special Publication 800-57 Part 1 Revision 4](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-57pt1r4.pdf) などの最新の推奨設定では、新しく生成されるキーの最小サイズとして 2,048 ビットが提案されています。</span><span class="sxs-lookup"><span data-stu-id="09754-114">Modern recommendations, such as [NIST Special Publication 800-57 Part 1 Revision 4](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-57pt1r4.pdf), suggest 2048-bit as the minimum size for newly generated keys.</span></span>

#### <a name="category"></a><span data-ttu-id="09754-115">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="09754-115">Category</span></span>

<span data-ttu-id="09754-116">暗号</span><span class="sxs-lookup"><span data-stu-id="09754-116">Cryptography</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="09754-117">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="09754-117">Affected APIs</span></span>

- <xref:System.Security.Cryptography.AsymmetricAlgorithm.LegalKeySizes?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSA.Create%2A?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSAOpenSsl.%23ctor%2A?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSACryptoServiceProvider.%23ctor%2A?displayProperty=nameWithType>

<!--
### Affected APIs

- `P:System.Security.Cryptography.AsymmetricAlgorithm.LegalKeySizes`
- `Overload:System.Security.Cryptography.RSA.Create`
- `Overload:System.Security.Cryptography.RSAOpenSsl.#ctor`
- `Overload:System.Security.Cryptography.RSACryptoServiceProvider.#ctor`


-->
