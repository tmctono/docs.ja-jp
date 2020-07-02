---
ms.openlocfilehash: c5a061dffa1deb66e1769d6ec70dfa2155ac6a31
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615709"
---
### <a name="calling-createdefaultauthorizationcontext-with-a-null-argument-has-changed"></a><span data-ttu-id="dc9d4-101">null 引数を指定した CreateDefaultAuthorizationContext の呼び出しが変更されました</span><span class="sxs-lookup"><span data-stu-id="dc9d4-101">Calling CreateDefaultAuthorizationContext with a null argument has changed</span></span>

#### <a name="details"></a><span data-ttu-id="dc9d4-102">説明</span><span class="sxs-lookup"><span data-stu-id="dc9d4-102">Details</span></span>

<span data-ttu-id="dc9d4-103">null の authorizationPolicies 引数を指定した <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext(System.Collections.Generic.IList{System.IdentityModel.Policy.IAuthorizationPolicy})?displayProperty=fullName> の呼び出しによって返される <xref:System.IdentityModel.Policy.AuthorizationContext?displayProperty=fullName> の実装が、.NET Framework 4.6 で変更されました。</span><span class="sxs-lookup"><span data-stu-id="dc9d4-103">The implementation of the <xref:System.IdentityModel.Policy.AuthorizationContext?displayProperty=fullName> returned by a call to the <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext(System.Collections.Generic.IList{System.IdentityModel.Policy.IAuthorizationPolicy})?displayProperty=fullName> with a null authorizationPolicies argument has changed its implementation in the .NET Framework 4.6.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="dc9d4-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="dc9d4-104">Suggestion</span></span>

<span data-ttu-id="dc9d4-105">まれに、カスタム認証を使用する WCF アプリの動作に違いが生じる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dc9d4-105">In rare cases, WCF apps that use custom authentication may see behavioral differences.</span></span> <span data-ttu-id="dc9d4-106">このような場合は、2 つの方法のいずれかで、以前の動作を復元できます。</span><span class="sxs-lookup"><span data-stu-id="dc9d4-106">In such cases, the previous behavior can be restored in either of two ways:</span></span>

- <span data-ttu-id="dc9d4-107">4\.6 よりも前のバージョンの .NET Framework を対象とするようにアプリを再コンパイルする。</span><span class="sxs-lookup"><span data-stu-id="dc9d4-107">Recompile your app to target an earlier version of the .NET Framework than 4.6.</span></span> <span data-ttu-id="dc9d4-108">IIS でホストされるサービスでは、`<httpRuntime targetFramework="x.x">` の要素を使用して、以前のバージョンの .NET Framework を対象とするようにします。</span><span class="sxs-lookup"><span data-stu-id="dc9d4-108">For IIS-hosted services, use the `<httpRuntime targetFramework="x.x">` element to target an earlier version of the .NET Framework.</span></span>
- <span data-ttu-id="dc9d4-109">app.config ファイルの `<appSettings>` セクションに以下の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="dc9d4-109">Add the following line to the `<appSettings>` section of your app.config file:</span></span>

    ```xml
    <add key="appContext.SetSwitch:Switch.System.IdentityModel.EnableCachedEmptyDefaultAuthorizationContext" value="true" />
    ```

| <span data-ttu-id="dc9d4-110">名前</span><span class="sxs-lookup"><span data-stu-id="dc9d4-110">Name</span></span>    | <span data-ttu-id="dc9d4-111">[値]</span><span class="sxs-lookup"><span data-stu-id="dc9d4-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="dc9d4-112">スコープ</span><span class="sxs-lookup"><span data-stu-id="dc9d4-112">Scope</span></span>   | <span data-ttu-id="dc9d4-113">マイナー</span><span class="sxs-lookup"><span data-stu-id="dc9d4-113">Minor</span></span>       |
| <span data-ttu-id="dc9d4-114">バージョン</span><span class="sxs-lookup"><span data-stu-id="dc9d4-114">Version</span></span> | <span data-ttu-id="dc9d4-115">4.6</span><span class="sxs-lookup"><span data-stu-id="dc9d4-115">4.6</span></span>         |
| <span data-ttu-id="dc9d4-116">種類</span><span class="sxs-lookup"><span data-stu-id="dc9d4-116">Type</span></span>    | <span data-ttu-id="dc9d4-117">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="dc9d4-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="dc9d4-118">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="dc9d4-118">Affected APIs</span></span>

- <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext(System.Collections.Generic.IList{System.IdentityModel.Policy.IAuthorizationPolicy})?displayProperty=nameWithType>
