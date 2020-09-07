---
ms.openlocfilehash: 4e685722271a8079e727ea9c2e0e501f68b30fc9
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496587"
---
### <a name="targetframeworkname-for-default-app-domain-no-longer-defaults-to-null-if-not-set"></a><span data-ttu-id="dba82-101">既定のアプリケーション ドメインの TargetFrameworkName は、設定されなかった場合、既定で null に設定されなくなった</span><span class="sxs-lookup"><span data-stu-id="dba82-101">TargetFrameworkName for default app domain no longer defaults to null if not set</span></span>

#### <a name="details"></a><span data-ttu-id="dba82-102">説明</span><span class="sxs-lookup"><span data-stu-id="dba82-102">Details</span></span>

<span data-ttu-id="dba82-103"><xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName> は、以前は、明示的に設定されない限り、既定のアプリケーション ドメインでは null でした。</span><span class="sxs-lookup"><span data-stu-id="dba82-103">The <xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName> was previously null in the default app domain, unless it was explicitly set.</span></span> <span data-ttu-id="dba82-104">4\.6 以降では、既定のアプリケーション ドメインの <xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName> プロパティは、TargetFrameworkAttribute (ある場合) から派生された既定値を持ちます。</span><span class="sxs-lookup"><span data-stu-id="dba82-104">Beginning in 4.6, the <xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName> property for the default app domain will have a default value derived from the TargetFrameworkAttribute (if one is present).</span></span> <span data-ttu-id="dba82-105">既定以外のアプリケーション ドメインは、明示的にオーバーライドされない限り、既定のアプリケーション ドメイン (4.6 では既定で null に設定されない) から <xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName> を継承し続けます。</span><span class="sxs-lookup"><span data-stu-id="dba82-105">Non-default app domains will continue to inherit their <xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName> from the default app domain (which will not default to null in 4.6) unless it is explicitly overridden.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="dba82-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="dba82-106">Suggestion</span></span>

<span data-ttu-id="dba82-107"><xref:System.AppDomainSetup.TargetFrameworkName> が既定で null に設定されることに依然しないように、コードを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dba82-107">Code should be updated to not depend on <xref:System.AppDomainSetup.TargetFrameworkName> defaulting to null.</span></span> <span data-ttu-id="dba82-108">このプロパティが引き続き null として評価される必要がある場合、明示的にその値に設定できます。</span><span class="sxs-lookup"><span data-stu-id="dba82-108">If it is required that this property continue to evaluate to null, it can be explicitly set to that value.</span></span>

| <span data-ttu-id="dba82-109">名前</span><span class="sxs-lookup"><span data-stu-id="dba82-109">Name</span></span>    | <span data-ttu-id="dba82-110">値</span><span class="sxs-lookup"><span data-stu-id="dba82-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="dba82-111">スコープ</span><span class="sxs-lookup"><span data-stu-id="dba82-111">Scope</span></span>   |<span data-ttu-id="dba82-112">エッジ</span><span class="sxs-lookup"><span data-stu-id="dba82-112">Edge</span></span>|
|<span data-ttu-id="dba82-113">バージョン</span><span class="sxs-lookup"><span data-stu-id="dba82-113">Version</span></span>|<span data-ttu-id="dba82-114">4.6</span><span class="sxs-lookup"><span data-stu-id="dba82-114">4.6</span></span>|
|<span data-ttu-id="dba82-115">種類</span><span class="sxs-lookup"><span data-stu-id="dba82-115">Type</span></span>|<span data-ttu-id="dba82-116">ランタイム</span><span class="sxs-lookup"><span data-stu-id="dba82-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="dba82-117">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="dba82-117">Affected APIs</span></span>

- <xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.AppDomainSetup.TargetFrameworkName`

-->
