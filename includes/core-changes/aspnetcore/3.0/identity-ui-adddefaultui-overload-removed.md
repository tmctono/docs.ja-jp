---
ms.openlocfilehash: 474f039cf00cb48761bfe7b7c4a0a9c6300cd820
ms.sourcegitcommit: d9470d8b2278b33108332c05224d86049cb9484b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/17/2020
ms.locfileid: "81637198"
---
### <a name="identity-adddefaultui-method-overload-removed"></a><span data-ttu-id="d9a3e-101">ID:AddDefaultUI メソッド オーバーロードが削除されました</span><span class="sxs-lookup"><span data-stu-id="d9a3e-101">Identity: AddDefaultUI method overload removed</span></span>

<span data-ttu-id="d9a3e-102">ASP.NET Core 3.0 以降では、[IdentityBuilderUIExtensions.AddDefaultUI(IdentityBuilder,UIFramework)](https://docs.microsoft.com/dotnet/api/microsoft.aspnetcore.identity.identitybuilderuiextensions.adddefaultui?view=aspnetcore-2.2#Microsoft_AspNetCore_Identity_IdentityBuilderUIExtensions_AddDefaultUI_Microsoft_AspNetCore_Identity_IdentityBuilder_Microsoft_AspNetCore_Identity_UI_UIFramework_) メソッド オーバーロードはなくなりました。</span><span class="sxs-lookup"><span data-stu-id="d9a3e-102">Starting with ASP.NET Core 3.0, the [IdentityBuilderUIExtensions.AddDefaultUI(IdentityBuilder,UIFramework)](https://docs.microsoft.com/dotnet/api/microsoft.aspnetcore.identity.identitybuilderuiextensions.adddefaultui?view=aspnetcore-2.2#Microsoft_AspNetCore_Identity_IdentityBuilderUIExtensions_AddDefaultUI_Microsoft_AspNetCore_Identity_IdentityBuilder_Microsoft_AspNetCore_Identity_UI_UIFramework_) method overload no longer exists.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="d9a3e-103">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="d9a3e-103">Version introduced</span></span>

<span data-ttu-id="d9a3e-104">3.0</span><span class="sxs-lookup"><span data-stu-id="d9a3e-104">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="d9a3e-105">変更理由</span><span class="sxs-lookup"><span data-stu-id="d9a3e-105">Reason for change</span></span>

<span data-ttu-id="d9a3e-106">この変更は、静的 Web アセット機能が導入された結果でした。</span><span class="sxs-lookup"><span data-stu-id="d9a3e-106">This change was a result of adoption of the static web assets feature.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="d9a3e-107">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="d9a3e-107">Recommended action</span></span>

<span data-ttu-id="d9a3e-108">2 つの引数を取るオーバーロードの代わりに <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)?displayProperty=nameWithType> を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="d9a3e-108">Call <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)?displayProperty=nameWithType> instead of the overload that takes two arguments.</span></span> <span data-ttu-id="d9a3e-109">ブートストラップ 3 を使用している場合、プロジェクト ファイルの `<PropertyGroup>` 要素に次の行も追加します。</span><span class="sxs-lookup"><span data-stu-id="d9a3e-109">If you're using Bootstrap 3, also add the following line to a `<PropertyGroup>` element in your project file:</span></span>

```xml
<IdentityUIFrameworkVersion>Bootstrap3</IdentityUIFrameworkVersion>
```

#### <a name="category"></a><span data-ttu-id="d9a3e-110">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="d9a3e-110">Category</span></span>

<span data-ttu-id="d9a3e-111">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="d9a3e-111">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d9a3e-112">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="d9a3e-112">Affected APIs</span></span>

[<span data-ttu-id="d9a3e-113">IdentityBuilderUIExtensions.AddDefaultUI(IdentityBuilder,UIFramework)</span><span class="sxs-lookup"><span data-stu-id="d9a3e-113">IdentityBuilderUIExtensions.AddDefaultUI(IdentityBuilder,UIFramework)</span></span>](https://docs.microsoft.com/dotnet/api/microsoft.aspnetcore.identity.identitybuilderuiextensions.adddefaultui?view=aspnetcore-2.2#Microsoft_AspNetCore_Identity_IdentityBuilderUIExtensions_AddDefaultUI_Microsoft_AspNetCore_Identity_IdentityBuilder_Microsoft_AspNetCore_Identity_UI_UIFramework_)

<!--

#### Affected APIs

`M:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)`

-->
