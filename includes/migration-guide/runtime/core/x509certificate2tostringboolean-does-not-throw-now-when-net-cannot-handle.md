---
ms.openlocfilehash: 7f8f97adcca7e66fa5756212bb977daadd92b8b6
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496281"
---
### <a name="x509certificate2tostringboolean-does-not-throw-now-when-net-cannot-handle-the-certificate"></a><span data-ttu-id="2f2e5-101">.NET で証明書を処理できないときに、X509Certificate2.ToString(Boolean) がスローしなくなった</span><span class="sxs-lookup"><span data-stu-id="2f2e5-101">X509Certificate2.ToString(Boolean) does not throw now when .NET cannot handle the certificate</span></span>

#### <a name="details"></a><span data-ttu-id="2f2e5-102">説明</span><span class="sxs-lookup"><span data-stu-id="2f2e5-102">Details</span></span>

<span data-ttu-id="2f2e5-103">.NET Framework 4.5.2 およびそれより前のバージョンでは、このメソッドは、verbose パラメーターとして <code>true</code> が渡され、.NET Framework ではサポートされない証明書がインストールされていた場合、スローしました。</span><span class="sxs-lookup"><span data-stu-id="2f2e5-103">In .NET Framework 4.5.2 and earlier versions, this method would throw if <code>true</code> was passed for the verbose parameter and there were certificates installed that weren't supported by the .NET Framework.</span></span> <span data-ttu-id="2f2e5-104">現在は、メソッドは成功し、証明書のアクセス不能部分を省いた有効な文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="2f2e5-104">Now, the method will succeed and return a valid string that omits the inaccessible portions of the certificate.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="2f2e5-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="2f2e5-105">Suggestion</span></span>

<span data-ttu-id="2f2e5-106"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType> に依存しているコードは、以前は API がスローしていたような場合には、返される文字列から一部の証明書データ (公開鍵、秘密鍵、拡張子など) が除外されることを予期するように更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f2e5-106">Any code depending on <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType> should be updated to expect that the returned string may exclude some certificate data (such as public key, private key, and extensions) in some cases in which the API would have previously thrown.</span></span>

| <span data-ttu-id="2f2e5-107">名前</span><span class="sxs-lookup"><span data-stu-id="2f2e5-107">Name</span></span>    | <span data-ttu-id="2f2e5-108">値</span><span class="sxs-lookup"><span data-stu-id="2f2e5-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="2f2e5-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="2f2e5-109">Scope</span></span>   |<span data-ttu-id="2f2e5-110">エッジ</span><span class="sxs-lookup"><span data-stu-id="2f2e5-110">Edge</span></span>|
|<span data-ttu-id="2f2e5-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="2f2e5-111">Version</span></span>|<span data-ttu-id="2f2e5-112">4.6</span><span class="sxs-lookup"><span data-stu-id="2f2e5-112">4.6</span></span>|
|<span data-ttu-id="2f2e5-113">種類</span><span class="sxs-lookup"><span data-stu-id="2f2e5-113">Type</span></span>|<span data-ttu-id="2f2e5-114">ランタイム</span><span class="sxs-lookup"><span data-stu-id="2f2e5-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="2f2e5-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="2f2e5-115">Affected APIs</span></span>

- <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)`

-->
