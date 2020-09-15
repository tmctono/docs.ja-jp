---
ms.openlocfilehash: abef47c64a7cfd99c5b50bf2100401a2d5fcc5c3
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614733"
---
### <a name="x509certificateclaimsetfindclaims-considers-all-claimtypes"></a><span data-ttu-id="6a0ac-101">X509CertificateClaimSet.FindClaims は、すべての claimTypes を考慮します</span><span class="sxs-lookup"><span data-stu-id="6a0ac-101">X509CertificateClaimSet.FindClaims Considers All claimTypes</span></span>

#### <a name="details"></a><span data-ttu-id="6a0ac-102">説明</span><span class="sxs-lookup"><span data-stu-id="6a0ac-102">Details</span></span>

<span data-ttu-id="6a0ac-103">X509 クレーム セットがその SAN フィールド内の複数の DNS エントリを含む証明書から初期化される場合は、.NET Framework 4.6.1 を対象とするアプリで、<xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=fullName>メソッドをすべての DNS エントリの claimType 引数と一致を試みます。 .NET Framework の以前のバージョンを対象とするアプリに対して、<xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=fullName>メソッドは claimType 引数と最後の DNS エントリのみを一致させようとしています。</span><span class="sxs-lookup"><span data-stu-id="6a0ac-103">In apps that target the .NET Framework 4.6.1, if an X509 claim set is initialized from a certificate that has multiple DNS entries in its SAN field, the <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=fullName> method attempts to match the claimType argument with all the DNS entries.For apps that target previous versions of the .NET Framework, the <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=fullName> method attempts to match the claimType argument only with the last DNS entry.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="6a0ac-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="6a0ac-104">Suggestion</span></span>

<span data-ttu-id="6a0ac-105">この変更は、.NET Framework 4.6.1 を対象とするアプリケーションのみに影響します。</span><span class="sxs-lookup"><span data-stu-id="6a0ac-105">This change only affects applications targeting the .NET Framework 4.6.1.</span></span> <span data-ttu-id="6a0ac-106">この変更は、[DisableMultipleDNSEntries](~/docs/framework/migration-guide/mitigation-x509certificateclaimset-findclaims-method.md#mitigation) 互換性スイッチで無効にできます (または、4.6.1 より前を対象としている場合は、有効にできます)。</span><span class="sxs-lookup"><span data-stu-id="6a0ac-106">This change may be disabled (or enabled if targeting pre-4.6.1) with the [DisableMultipleDNSEntries](~/docs/framework/migration-guide/mitigation-x509certificateclaimset-findclaims-method.md#mitigation) compatibility switch.</span></span>

| <span data-ttu-id="6a0ac-107">名前</span><span class="sxs-lookup"><span data-stu-id="6a0ac-107">Name</span></span>    | <span data-ttu-id="6a0ac-108">[値]</span><span class="sxs-lookup"><span data-stu-id="6a0ac-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="6a0ac-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="6a0ac-109">Scope</span></span>   | <span data-ttu-id="6a0ac-110">マイナー</span><span class="sxs-lookup"><span data-stu-id="6a0ac-110">Minor</span></span>       |
| <span data-ttu-id="6a0ac-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="6a0ac-111">Version</span></span> | <span data-ttu-id="6a0ac-112">4.6.1</span><span class="sxs-lookup"><span data-stu-id="6a0ac-112">4.6.1</span></span>       |
| <span data-ttu-id="6a0ac-113">種類</span><span class="sxs-lookup"><span data-stu-id="6a0ac-113">Type</span></span>    | <span data-ttu-id="6a0ac-114">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="6a0ac-114">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="6a0ac-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="6a0ac-115">Affected APIs</span></span>

- <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=nameWithType>
