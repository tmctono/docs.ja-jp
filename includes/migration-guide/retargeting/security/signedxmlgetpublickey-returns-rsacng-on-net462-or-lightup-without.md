---
ms.openlocfilehash: 23e278d38d6904d8afe927e6b54c388d443e41f5
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616093"
---
### <a name="signedxmlgetpublickey-returns-rsacng-on-net462-or-lightup-without-retargeting-change"></a><span data-ttu-id="6f109-101">変更の対象を変更せず、SignedXml.GetPublicKey が net462 (または Light-Up) で RSACng を返す</span><span class="sxs-lookup"><span data-stu-id="6f109-101">SignedXml.GetPublicKey returns RSACng on net462 (or lightup) without retargeting change</span></span>

#### <a name="details"></a><span data-ttu-id="6f109-102">説明</span><span class="sxs-lookup"><span data-stu-id="6f109-102">Details</span></span>

<span data-ttu-id="6f109-103">.NET Framework 4.6.2 より、<xref:System.Security.Cryptography.Xml.SignedXml.GetPublicKey%2A?displayProperty=nameWithType> メソッドによって返されるオブジェクトの具象型が CryptoServiceProvider 実装から Cng 実装に変わりました。これは突然の変更ではなく、</span><span class="sxs-lookup"><span data-stu-id="6f109-103">Starting with the .NET Framework 4.6.2, the concrete type of the object returned by the <xref:System.Security.Cryptography.Xml.SignedXml.GetPublicKey%2A?displayProperty=nameWithType> method changed (without a quirk) from a CryptoServiceProvider implementation to a Cng implementation.</span></span> <span data-ttu-id="6f109-104">`certificate.PublicKey.Key` の使用から、`certificate.GetAnyPublicKey` に転送する内部 <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey%2A?displayProperty=nameWithType> の使用に実装が変わったためです。</span><span class="sxs-lookup"><span data-stu-id="6f109-104">This is because the implementation changed from using `certificate.PublicKey.Key` to using the internal `certificate.GetAnyPublicKey` which forwards to <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey%2A?displayProperty=nameWithType>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="6f109-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="6f109-105">Suggestion</span></span>

<span data-ttu-id="6f109-106">.NET Framework 4.7.1 で実行されるアプリから、アプリの構成ファイルの [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) セクションに次の構成スイッチを追加することで、.NET Framework 4.6.1 以前のバージョンで既定で使用されていた CryptoServiceProvider 実装を使用できます。</span><span class="sxs-lookup"><span data-stu-id="6f109-106">Starting with apps running on the .NET Framework 4.7.1, you can use the CryptoServiceProvider implementation used by default in the .NET Framework 4.6.1 and earlier versions by adding the following configuration switch to the [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your app config file:</span></span>

```xml
<AppContextSwitchOverrides value="Switch.System.Security.Cryptography.Xml.SignedXmlUseLegacyCertificatePrivateKey=true" />
```

| <span data-ttu-id="6f109-107">名前</span><span class="sxs-lookup"><span data-stu-id="6f109-107">Name</span></span>    | <span data-ttu-id="6f109-108">値</span><span class="sxs-lookup"><span data-stu-id="6f109-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="6f109-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="6f109-109">Scope</span></span>   | <span data-ttu-id="6f109-110">エッジ</span><span class="sxs-lookup"><span data-stu-id="6f109-110">Edge</span></span>        |
| <span data-ttu-id="6f109-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="6f109-111">Version</span></span> | <span data-ttu-id="6f109-112">4.6.2</span><span class="sxs-lookup"><span data-stu-id="6f109-112">4.6.2</span></span>       |
| <span data-ttu-id="6f109-113">種類</span><span class="sxs-lookup"><span data-stu-id="6f109-113">Type</span></span>    | <span data-ttu-id="6f109-114">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="6f109-114">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="6f109-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="6f109-115">Affected APIs</span></span>

- <xref:System.Security.Cryptography.Xml.SignedXml.CheckSignatureReturningKey(System.Security.Cryptography.AsymmetricAlgorithm@)?displayProperty=nameWithType>
