---
ms.openlocfilehash: c5e4b5619394f99a419fe48aee190ad741ea8c0d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "73041660"
---
### <a name="identity-ui-uses-static-web-assets-feature"></a><span data-ttu-id="cae08-101">ID:UI で静的な Web 資産機能を使用</span><span class="sxs-lookup"><span data-stu-id="cae08-101">Identity: UI uses static web assets feature</span></span>

<span data-ttu-id="cae08-102">ASP.NET Core 3.0 では静的な Web 資産機能が導入され、ID UI でこれが導入されました。</span><span class="sxs-lookup"><span data-stu-id="cae08-102">ASP.NET Core 3.0 introduced a static web assets feature, and Identity UI has adopted it.</span></span>

#### <a name="change-description"></a><span data-ttu-id="cae08-103">変更の説明</span><span class="sxs-lookup"><span data-stu-id="cae08-103">Change description</span></span>

<span data-ttu-id="cae08-104">ID UI で静的な Web 資産機能が導入された結果として、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="cae08-104">As a result of Identity UI adopting the static web assets feature:</span></span>

- <span data-ttu-id="cae08-105">フレームワークの選択は、プロジェクト ファイルで `IdentityUIFrameworkVersion` プロパティを使用して行います。</span><span class="sxs-lookup"><span data-stu-id="cae08-105">Framework selection is accomplished by using the `IdentityUIFrameworkVersion` property in your project file.</span></span>
- <span data-ttu-id="cae08-106">Bootstrap 4 が、ID UI の既定の UI フレームワークです。</span><span class="sxs-lookup"><span data-stu-id="cae08-106">Bootstrap 4 is the default UI framework for Identity UI.</span></span> <span data-ttu-id="cae08-107">Bootstrap 3 はサポートが終了したので、サポートされているバージョンへの移行を検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cae08-107">Bootstrap 3 has reached end of life, and you should consider migrating to a supported version.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="cae08-108">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="cae08-108">Version introduced</span></span>

<span data-ttu-id="cae08-109">3.0</span><span class="sxs-lookup"><span data-stu-id="cae08-109">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="cae08-110">以前の動作</span><span class="sxs-lookup"><span data-stu-id="cae08-110">Old behavior</span></span>

<span data-ttu-id="cae08-111">ID UI の既定の UI フレームワークは **Bootstrap 3** でした。</span><span class="sxs-lookup"><span data-stu-id="cae08-111">The default UI framework for Identity UI was **Bootstrap 3**.</span></span> <span data-ttu-id="cae08-112">UI フレームワークは、`Startup.ConfigureServices` で `AddDefaultUI` メソッド呼び出しのパラメーターを使用して構成できました。</span><span class="sxs-lookup"><span data-stu-id="cae08-112">The UI framework could be configured using a parameter to the `AddDefaultUI` method call in `Startup.ConfigureServices`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="cae08-113">新しい動作</span><span class="sxs-lookup"><span data-stu-id="cae08-113">New behavior</span></span>

<span data-ttu-id="cae08-114">ID UI の既定の UI フレームワークは **Bootstrap 4** です。</span><span class="sxs-lookup"><span data-stu-id="cae08-114">The default UI framework for Identity UI is **Bootstrap 4**.</span></span> <span data-ttu-id="cae08-115">UI フレームワークは、`AddDefaultUI` メソッド呼び出し内ではなく、プロジェクト ファイル内で構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cae08-115">The UI framework must be configured in your project file, instead of in the `AddDefaultUI` method call.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="cae08-116">変更理由</span><span class="sxs-lookup"><span data-stu-id="cae08-116">Reason for change</span></span>

<span data-ttu-id="cae08-117">静的な Web 資産機能を導入するには、UI フレームワークの構成を MSBuild に移行する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="cae08-117">Adoption of the static web assets feature required that the UI framework configuration move to MSBuild.</span></span> <span data-ttu-id="cae08-118">埋め込むフレームワークは、実行時に決定されるのではなく、ビルド時に決定されます。</span><span class="sxs-lookup"><span data-stu-id="cae08-118">The decision on which framework to embed is a build-time decision, not a runtime decision.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="cae08-119">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="cae08-119">Recommended action</span></span>

<span data-ttu-id="cae08-120">サイトの UI を見直して、新しい Bootstrap 4 コンポーネントに互換性があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cae08-120">Review your site UI to ensure the new Bootstrap 4 components are compatible.</span></span> <span data-ttu-id="cae08-121">必要に応じて、`IdentityUIFrameworkVersion` MSBuild プロパティを使用して Bootstrap 3 に戻します。</span><span class="sxs-lookup"><span data-stu-id="cae08-121">If necessary, use the `IdentityUIFrameworkVersion` MSBuild property to revert to Bootstrap 3.</span></span> <span data-ttu-id="cae08-122">このプロパティを、プロジェクト ファイルの `<PropertyGroup>` 要素に追加します。</span><span class="sxs-lookup"><span data-stu-id="cae08-122">Add the property to a `<PropertyGroup>` element in your project file:</span></span>

```xml
<IdentityUIFrameworkVersion>Bootstrap3</IdentityUIFrameworkVersion>
```

#### <a name="category"></a><span data-ttu-id="cae08-123">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="cae08-123">Category</span></span>

<span data-ttu-id="cae08-124">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="cae08-124">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="cae08-125">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="cae08-125">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)?displayProperty=nameWithType>

<!-- 

#### Affected APIs

`M:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)`

-->
