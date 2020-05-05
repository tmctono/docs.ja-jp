---
ms.openlocfilehash: 6deeb7debce9b731f3871b7de0ad8df8a8cdafea
ms.sourcegitcommit: 7370aa8203b6036cea1520021b5511d0fd994574
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/02/2020
ms.locfileid: "82728287"
---
### <a name="localization-resourcemanagerwithculturestringlocalizer-class-and-withculture-interface-member-removed"></a><span data-ttu-id="d8b60-101">ローカリゼーション:ResourceManagerWithCultureStringLocalizer クラスと WithCulture インターフェイス メンバーを削除</span><span class="sxs-lookup"><span data-stu-id="d8b60-101">Localization: ResourceManagerWithCultureStringLocalizer class and WithCulture interface member removed</span></span>

<span data-ttu-id="d8b60-102">.NET 5.0 Preview 1 で [ResourceManagerWithCultureStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1) クラスと [WithCulture](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1) メソッドが削除されました。</span><span class="sxs-lookup"><span data-stu-id="d8b60-102">The [ResourceManagerWithCultureStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1) class and [WithCulture](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1) method were removed in .NET 5.0 Preview 1.</span></span>

<span data-ttu-id="d8b60-103">コンテキストについては、[aspnet/Announcements#346](https://github.com/aspnet/Announcements/issues/346) と [dotnet/aspnetcore#3324](https://github.com/dotnet/aspnetcore/issues/3324) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8b60-103">For context, see [aspnet/Announcements#346](https://github.com/aspnet/Announcements/issues/346) and [dotnet/aspnetcore#3324](https://github.com/dotnet/aspnetcore/issues/3324).</span></span> <span data-ttu-id="d8b60-104">この変更のディスカッションについては、[dotnet/aspnetcore#7756](https://github.com/dotnet/aspnetcore/issues/7756) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8b60-104">For discussion on this change, see [dotnet/aspnetcore#7756](https://github.com/dotnet/aspnetcore/issues/7756).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="d8b60-105">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="d8b60-105">Version introduced</span></span>

<span data-ttu-id="d8b60-106">5.0 Preview 1</span><span class="sxs-lookup"><span data-stu-id="d8b60-106">5.0 Preview 1</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="d8b60-107">以前の動作</span><span class="sxs-lookup"><span data-stu-id="d8b60-107">Old behavior</span></span>

<span data-ttu-id="d8b60-108">`ResourceManagerWithCultureStringLocalizer` クラスと `ResourceManagerStringLocalizer.WithCulture` メソッドは、[.NET Core 3.0 Preview 3 以降、古い形式となりました](/dotnet/core/compatibility/2.2-3.0#localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete)。</span><span class="sxs-lookup"><span data-stu-id="d8b60-108">The `ResourceManagerWithCultureStringLocalizer` class and the `ResourceManagerStringLocalizer.WithCulture` method are [obsolete in .NET Core 3.0 Preview 3 and later](/dotnet/core/compatibility/2.2-3.0#localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete).</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="d8b60-109">新しい動作</span><span class="sxs-lookup"><span data-stu-id="d8b60-109">New behavior</span></span>

<span data-ttu-id="d8b60-110">`ResourceManagerWithCultureStringLocalizer` クラスと `ResourceManagerStringLocalizer.WithCulture` メソッドは、.NET 5.0 Preview 1 で削除されています。</span><span class="sxs-lookup"><span data-stu-id="d8b60-110">The `ResourceManagerWithCultureStringLocalizer` class and the `ResourceManagerStringLocalizer.WithCulture` method have been removed in .NET 5.0 Preview 1.</span></span> <span data-ttu-id="d8b60-111">加えられた変更のインベントリについては、[dotnet/extensions#2562](https://github.com/dotnet/extensions/pull/2562/files) の pull request を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8b60-111">For an inventory of the changes made, see the pull request at [dotnet/extensions#2562](https://github.com/dotnet/extensions/pull/2562/files).</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="d8b60-112">変更理由</span><span class="sxs-lookup"><span data-stu-id="d8b60-112">Reason for change</span></span>

<span data-ttu-id="d8b60-113">[ResourceManagerWithCultureStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1) クラスと [ResourceManagerStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1) メソッドは、ローカライズでユーザーの混乱の原因になることがよくありました。</span><span class="sxs-lookup"><span data-stu-id="d8b60-113">The [ResourceManagerWithCultureStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1) class and [ResourceManagerStringLocalizer.WithCulture](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1) method were often sources of confusion for users of localization.</span></span> <span data-ttu-id="d8b60-114">カスタムの <xref:Microsoft.Extensions.Localization.IStringLocalizer> 実装を作成する際は、混乱に拍車がかかっていました。</span><span class="sxs-lookup"><span data-stu-id="d8b60-114">The confusion was especially high when creating a custom <xref:Microsoft.Extensions.Localization.IStringLocalizer> implementation.</span></span> <span data-ttu-id="d8b60-115">このクラスとメソッドを使用すると、`IStringLocalizer` インスタンスが "言語ごとで、リソースごと" であるような印象をコンシューマーに与えるのです。</span><span class="sxs-lookup"><span data-stu-id="d8b60-115">This class and method give consumers the impression that an `IStringLocalizer` instance is expected to be "per-language, per-resource".</span></span> <span data-ttu-id="d8b60-116">実際には、インスタンスは "リソースごと" のみである必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8b60-116">In reality, the instance should only be "per-resource".</span></span> <span data-ttu-id="d8b60-117">実行時に、<xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType> プロパティによって、使用言語が決定されます。</span><span class="sxs-lookup"><span data-stu-id="d8b60-117">At run time, the <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType> property determines the language to be used.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="d8b60-118">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="d8b60-118">Recommended action</span></span>

<span data-ttu-id="d8b60-119">`ResourceManagerWithCultureStringLocalizer` クラスと `ResourceManagerStringLocalizer.WithCulture` メソッドの使用をやめます。</span><span class="sxs-lookup"><span data-stu-id="d8b60-119">Stop using the `ResourceManagerWithCultureStringLocalizer` class and the `ResourceManagerStringLocalizer.WithCulture` method.</span></span>

#### <a name="category"></a><span data-ttu-id="d8b60-120">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="d8b60-120">Category</span></span>

<span data-ttu-id="d8b60-121">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="d8b60-121">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d8b60-122">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="d8b60-122">Affected APIs</span></span>

- [<span data-ttu-id="d8b60-123">ResourceManagerWithCultureStringLocalizer</span><span class="sxs-lookup"><span data-stu-id="d8b60-123">ResourceManagerWithCultureStringLocalizer</span></span>](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1)
- [<span data-ttu-id="d8b60-124">ResourceManagerStringLocalizer.WithCulture</span><span class="sxs-lookup"><span data-stu-id="d8b60-124">ResourceManagerStringLocalizer.WithCulture</span></span>](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1)

<!--

#### Affected APIs

- `T:Microsoft.Extensions.Localization.ResourceManagerWithCultureStringLocalizer`
- `Overload:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.WithCulture`

-->
