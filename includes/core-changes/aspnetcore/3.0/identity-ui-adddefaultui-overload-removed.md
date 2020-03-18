---
ms.openlocfilehash: 806722ea9aec1c828786525e3155b7f624159ac1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "72522659"
---
### <a name="identity-adddefaultui-method-overload-removed"></a><span data-ttu-id="4ab8b-101">ID:AddDefaultUI メソッド オーバーロードが削除されました</span><span class="sxs-lookup"><span data-stu-id="4ab8b-101">Identity: AddDefaultUI method overload removed</span></span>

<span data-ttu-id="4ab8b-102">ASP.NET Core 3.0 から、<xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)?displayProperty=nameWithType> メソッド オーバーロードがなくなりました。</span><span class="sxs-lookup"><span data-stu-id="4ab8b-102">Starting with ASP.NET Core 3.0, the <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)?displayProperty=nameWithType> method overload no longer exists.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="4ab8b-103">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="4ab8b-103">Version introduced</span></span>

<span data-ttu-id="4ab8b-104">3.0</span><span class="sxs-lookup"><span data-stu-id="4ab8b-104">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="4ab8b-105">変更理由</span><span class="sxs-lookup"><span data-stu-id="4ab8b-105">Reason for change</span></span>

<span data-ttu-id="4ab8b-106">この変更は、静的 Web アセット機能が導入された結果でした。</span><span class="sxs-lookup"><span data-stu-id="4ab8b-106">This change was a result of adoption of the static web assets feature.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="4ab8b-107">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="4ab8b-107">Recommended action</span></span>

<span data-ttu-id="4ab8b-108">オーバーロードではなく、<xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)?displayProperty=nameWithType> を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4ab8b-108">Call <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)?displayProperty=nameWithType> instead of the overload.</span></span> <span data-ttu-id="4ab8b-109">ブートストラップ 3 を使用している場合、プロジェクト ファイルの `<PropertyGroup>` 要素に次の行も追加します。</span><span class="sxs-lookup"><span data-stu-id="4ab8b-109">If you're using Bootstrap 3, also add the following line to a `<PropertyGroup>` element in your project file:</span></span>

```xml
<IdentityUIFrameworkVersion>Bootstrap3</IdentityUIFrameworkVersion>
```

#### <a name="category"></a><span data-ttu-id="4ab8b-110">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="4ab8b-110">Category</span></span>

<span data-ttu-id="4ab8b-111">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="4ab8b-111">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="4ab8b-112">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="4ab8b-112">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)?displayProperty=fullName>

<!--

#### Affected APIs

`M:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)`

-->
