---
ms.openlocfilehash: 878aef544b2706bfd10a3dddce1b902655ef003a
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58761043"
---
### <a name="x509certificateclaimsetfindclaims-considers-all-claimtypes"></a><span data-ttu-id="dc7c2-101">X509CertificateClaimSet.FindClaims は、すべての claimTypes を考慮します</span><span class="sxs-lookup"><span data-stu-id="dc7c2-101">X509CertificateClaimSet.FindClaims Considers All claimTypes</span></span>

|   |   |
|---|---|
|<span data-ttu-id="dc7c2-102">説明</span><span class="sxs-lookup"><span data-stu-id="dc7c2-102">Details</span></span>|<span data-ttu-id="dc7c2-103">X509 クレーム セットがその SAN フィールド内の複数の DNS エントリを含む証明書から初期化される場合は、.NET Framework 4.6.1 を対象とするアプリで、<xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=name>メソッドをすべての DNS エントリの claimType 引数と一致を試みます。 .NET Framework の以前のバージョンを対象とするアプリに対して、<xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=name>メソッドは claimType 引数と最後の DNS エントリのみを一致させようとしています。</span><span class="sxs-lookup"><span data-stu-id="dc7c2-103">In apps that target the .NET Framework 4.6.1, if an X509 claim set is initialized from a certificate that has multiple DNS entries in its SAN field, the <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=name> method attempts to match the claimType argument with all the DNS entries.For apps that target previous versions of the .NET Framework, the <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=name> method attempts to match the claimType argument only with the last DNS entry.</span></span>|
|<span data-ttu-id="dc7c2-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="dc7c2-104">Suggestion</span></span>|<span data-ttu-id="dc7c2-105">この変更は、.NET Framework 4.6.1 を対象とするアプリケーションのみに影響します。</span><span class="sxs-lookup"><span data-stu-id="dc7c2-105">This change only affects applications targeting the .NET Framework 4.6.1.</span></span> <span data-ttu-id="dc7c2-106">この変更は、[DisableMultipleDNSEntries](~/docs/framework/migration-guide/mitigation-x509certificateclaimset-findclaims-method.md#mitigation) 互換性スイッチで無効にできます (または、4.6.1 より前を対象としている場合は、有効にできます)。</span><span class="sxs-lookup"><span data-stu-id="dc7c2-106">This change may be disabled (or enabled if targeting pre-4.6.1) with the [DisableMultipleDNSEntries](~/docs/framework/migration-guide/mitigation-x509certificateclaimset-findclaims-method.md#mitigation) compatibility switch.</span></span>|
|<span data-ttu-id="dc7c2-107">スコープ</span><span class="sxs-lookup"><span data-stu-id="dc7c2-107">Scope</span></span>|<span data-ttu-id="dc7c2-108">マイナー</span><span class="sxs-lookup"><span data-stu-id="dc7c2-108">Minor</span></span>|
|<span data-ttu-id="dc7c2-109">Version</span><span class="sxs-lookup"><span data-stu-id="dc7c2-109">Version</span></span>|<span data-ttu-id="dc7c2-110">4.6.1</span><span class="sxs-lookup"><span data-stu-id="dc7c2-110">4.6.1</span></span>|
|<span data-ttu-id="dc7c2-111">型</span><span class="sxs-lookup"><span data-stu-id="dc7c2-111">Type</span></span>|<span data-ttu-id="dc7c2-112">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="dc7c2-112">Retargeting</span></span>|
|<span data-ttu-id="dc7c2-113">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="dc7c2-113">Affected APIs</span></span>|<ul><li><xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=nameWithType></li></ul>|

