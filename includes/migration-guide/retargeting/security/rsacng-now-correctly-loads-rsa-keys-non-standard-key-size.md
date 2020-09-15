---
ms.openlocfilehash: c1e85941c8c6c31c7d937d0671ad955fa6490783
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614649"
---
### <a name="rsacng-now-correctly-loads-rsa-keys-of-non-standard-key-size"></a><span data-ttu-id="3d73c-101">RSACng でキー サイズが非標準の RSA キーが正しく読み込まれるようになりました</span><span class="sxs-lookup"><span data-stu-id="3d73c-101">RSACng now correctly loads RSA keys of non-standard key size</span></span>

#### <a name="details"></a><span data-ttu-id="3d73c-102">説明</span><span class="sxs-lookup"><span data-stu-id="3d73c-102">Details</span></span>

<span data-ttu-id="3d73c-103">4\.6.2 より前の .NET Framework バージョンでは、RSA 証明書のキー サイズが標準ではない顧客は、拡張メソッドの <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=fullName> や <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=fullName> でそのキーにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="3d73c-103">In .NET Framework versions prior to 4.6.2, customers with non-standard key sizes for RSA certificates are unable to access those keys via the <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=fullName> and <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=fullName> extension methods.</span></span>  <span data-ttu-id="3d73c-104">&quot;The requested key size is not supported (要求されたサイズのキーには対応していません)&quot; というメッセージと共に <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="3d73c-104">A <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName> with the message &quot;The requested key size is not supported&quot; is thrown.</span></span> <span data-ttu-id="3d73c-105">.NET Framework 4.6.2 では、この問題が修正されました。</span><span class="sxs-lookup"><span data-stu-id="3d73c-105">In .NET Framework 4.6.2 this issue has been fixed.</span></span> <span data-ttu-id="3d73c-106">同様に、<xref:System.Security.Cryptography.RSA.ImportParameters(System.Security.Cryptography.RSAParameters)> と <xref:System.Security.Cryptography.RSACng.ImportParameters(System.Security.Cryptography.RSAParameters)> で <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName> をスローすることなく非標準サイズのキーが処理されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="3d73c-106">Similarly, <xref:System.Security.Cryptography.RSA.ImportParameters(System.Security.Cryptography.RSAParameters)> and <xref:System.Security.Cryptography.RSACng.ImportParameters(System.Security.Cryptography.RSAParameters)> now work with non-standard key sizes without throwing a <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="3d73c-107">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="3d73c-107">Suggestion</span></span>

<span data-ttu-id="3d73c-108">非標準サイズのキーが使用されるときに <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName> がスローされるという以前の動作に依存する例外処理ロジックがある場合、そのロジックを除くことを検討してください。</span><span class="sxs-lookup"><span data-stu-id="3d73c-108">If there is any exception handling logic that relies on the previous behavior where a <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName> is thrown when non-standard key sizes are used, consider removing the logic.</span></span>

| <span data-ttu-id="3d73c-109">名前</span><span class="sxs-lookup"><span data-stu-id="3d73c-109">Name</span></span>    | <span data-ttu-id="3d73c-110">値</span><span class="sxs-lookup"><span data-stu-id="3d73c-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="3d73c-111">スコープ</span><span class="sxs-lookup"><span data-stu-id="3d73c-111">Scope</span></span>   | <span data-ttu-id="3d73c-112">エッジ</span><span class="sxs-lookup"><span data-stu-id="3d73c-112">Edge</span></span>        |
| <span data-ttu-id="3d73c-113">バージョン</span><span class="sxs-lookup"><span data-stu-id="3d73c-113">Version</span></span> | <span data-ttu-id="3d73c-114">4.6.2</span><span class="sxs-lookup"><span data-stu-id="3d73c-114">4.6.2</span></span>       |
| <span data-ttu-id="3d73c-115">種類</span><span class="sxs-lookup"><span data-stu-id="3d73c-115">Type</span></span>    | <span data-ttu-id="3d73c-116">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="3d73c-116">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="3d73c-117">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="3d73c-117">Affected APIs</span></span>

- <xref:System.Security.Cryptography.RSA.ImportParameters(System.Security.Cryptography.RSAParameters)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSACng.ImportParameters(System.Security.Cryptography.RSAParameters)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=nameWithType>
