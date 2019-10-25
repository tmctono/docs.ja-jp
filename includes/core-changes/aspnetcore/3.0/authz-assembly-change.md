---
ms.openlocfilehash: 65bac44c84589fb55d2b04c39088c2825c451a6b
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2019
ms.locfileid: "72393951"
---
### <a name="authorization-addauthorization-overload-moved-to-different-assembly"></a><span data-ttu-id="2be61-101">Authorization:AddAuthorization のオーバーロードが別のアセンブリに移動した</span><span class="sxs-lookup"><span data-stu-id="2be61-101">Authorization: AddAuthorization overload moved to different assembly</span></span>

<span data-ttu-id="2be61-102">`Microsoft.AspNetCore.Authorization` に以前あったコア `AddAuthorization` メソッドが `AddAuthorizationCore` に名前変更されました。</span><span class="sxs-lookup"><span data-stu-id="2be61-102">The core `AddAuthorization` methods that used to reside in `Microsoft.AspNetCore.Authorization` were renamed to `AddAuthorizationCore`.</span></span> <span data-ttu-id="2be61-103">古い `AddAuthorization` メソッドはまだありますが、代わりに `Microsoft.AspNetCore.Authorization.Policy` パッケージに含まれています。</span><span class="sxs-lookup"><span data-stu-id="2be61-103">The old `AddAuthorization` methods still exist, but are in the `Microsoft.AspNetCore.Authorization.Policy` package instead.</span></span> <span data-ttu-id="2be61-104">両方のメソッドを使用するアプリには影響はありません。</span><span class="sxs-lookup"><span data-stu-id="2be61-104">Apps using both methods should see no impact.</span></span> <span data-ttu-id="2be61-105">ポリシー パッケージを使用していないアプリは、`AddAuthorizationCore` を使用するように切り替える必要があります。</span><span class="sxs-lookup"><span data-stu-id="2be61-105">Apps that weren't using the policy package must switch to using `AddAuthorizationCore`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="2be61-106">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="2be61-106">Version introduced</span></span>

<span data-ttu-id="2be61-107">3.0</span><span class="sxs-lookup"><span data-stu-id="2be61-107">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="2be61-108">以前の動作</span><span class="sxs-lookup"><span data-stu-id="2be61-108">Old behavior</span></span>

<span data-ttu-id="2be61-109">`AddAuthorization` メソッドは `Microsoft.AspNetCore.Authorization` にありました。</span><span class="sxs-lookup"><span data-stu-id="2be61-109">`AddAuthorization` methods existed in `Microsoft.AspNetCore.Authorization`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="2be61-110">新しい動作</span><span class="sxs-lookup"><span data-stu-id="2be61-110">New behavior</span></span>

<span data-ttu-id="2be61-111">`AddAuthorization` メソッドは `Microsoft.AspNetCore.Authorization.Policy` にあります。</span><span class="sxs-lookup"><span data-stu-id="2be61-111">`AddAuthorization` methods exist in `Microsoft.AspNetCore.Authorization.Policy`.</span></span> <span data-ttu-id="2be61-112">`AddAuthorizationCore` は、古いメソッドの新しい名前です。</span><span class="sxs-lookup"><span data-stu-id="2be61-112">`AddAuthorizationCore` is the new name for the old methods.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="2be61-113">変更理由</span><span class="sxs-lookup"><span data-stu-id="2be61-113">Reason for change</span></span>

<span data-ttu-id="2be61-114">`AddAuthorization` は、承認に必要な一般的なすべてのサービスを追加するのにより適切なメソッド名です。</span><span class="sxs-lookup"><span data-stu-id="2be61-114">`AddAuthorization` is a better method name for adding all common services needed for authorization.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="2be61-115">推奨される操作</span><span class="sxs-lookup"><span data-stu-id="2be61-115">Recommended action</span></span>

<span data-ttu-id="2be61-116">`Microsoft.AspNetCore.Authorization.Policy` に参照を追加するか、代わりに `AddAuthorizationCore` を使用します。</span><span class="sxs-lookup"><span data-stu-id="2be61-116">Either add a reference to `Microsoft.AspNetCore.Authorization.Policy` or use `AddAuthorizationCore` instead.</span></span>

#### <a name="category"></a><span data-ttu-id="2be61-117">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="2be61-117">Category</span></span>

<span data-ttu-id="2be61-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="2be61-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="2be61-119">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="2be61-119">Affected APIs</span></span>

<xref:Microsoft.Extensions.DependencyInjection.AuthorizationServiceCollectionExtensions.AddAuthorization(Microsoft.Extensions.DependencyInjection.IServiceCollection,System.Action{Microsoft.AspNetCore.Authorization.AuthorizationOptions})?displayProperty=fullName>

<!--

#### Affected APIs

`M:Microsoft.Extensions.DependencyInjection.AuthorizationServiceCollectionExtensions.AddAuthorization(Microsoft.Extensions.DependencyInjection.IServiceCollection,System.Action{Microsoft.AspNetCore.Authorization.AuthorizationOptions})`

-->
