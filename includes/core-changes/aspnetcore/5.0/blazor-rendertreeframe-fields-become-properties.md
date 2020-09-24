---
ms.openlocfilehash: edff55d540f08e8a9fd4d0687aaf6bd963ee3a84
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90539533"
---
### <a name="blazor-rendertreeframe-readonly-public-fields-have-become-properties"></a><span data-ttu-id="a87df-101">Blazor: RenderTreeFrame の readonly のパブリック フィールドのプロパティ化</span><span class="sxs-lookup"><span data-stu-id="a87df-101">Blazor: RenderTreeFrame readonly public fields have become properties</span></span>

<span data-ttu-id="a87df-102">ASP.NET Core 3.0 および 3.1 の <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame> 構造体では、<xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.FrameType>、<xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.Sequence> などのさまざまな `readonly public` フィールドが公開されています。</span><span class="sxs-lookup"><span data-stu-id="a87df-102">In ASP.NET Core 3.0 and 3.1, the <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame> struct exposed various `readonly public` fields, including <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.FrameType>, <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.Sequence>, and others.</span></span> <span data-ttu-id="a87df-103">このすべての `readonly public` フィールドが、ASP.NET Core 5.0 RC1 以降のバージョンで、`readonly public` プロパティに変更されています。</span><span class="sxs-lookup"><span data-stu-id="a87df-103">In ASP.NET Core 5.0 RC1 and later versions, all the `readonly public` fields changed to `readonly public` properties.</span></span>

<span data-ttu-id="a87df-104">この変更は、次の理由により多くの開発者に影響しません。</span><span class="sxs-lookup"><span data-stu-id="a87df-104">This change won't affect many developers because:</span></span>

* <span data-ttu-id="a87df-105">コンポーネントの定義に単純に `.razor` ファイルを使用する (または <xref:Microsoft.AspNetCore.Components.Rendering.RenderTreeBuilder> を手動で呼び出す) どのアプリまたはライブラリでも、この型は直接参照されません。</span><span class="sxs-lookup"><span data-stu-id="a87df-105">Any app or library that simply uses `.razor` files (or even manual <xref:Microsoft.AspNetCore.Components.Rendering.RenderTreeBuilder> calls) to define its components wouldn't be referencing this type directly.</span></span>
* <span data-ttu-id="a87df-106">`RenderTreeFrame` 型自体が実装の詳細と見なされ、フレームワーク外で使用するものとはみなされていません。</span><span class="sxs-lookup"><span data-stu-id="a87df-106">The `RenderTreeFrame` type itself is regarded as an implementation detail, not intended for use outside of the framework.</span></span> <span data-ttu-id="a87df-107">ASP.NET Core 3.0 以降には、型が直接使用される場合にコンパイラ警告が発行されるアナライザーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a87df-107">ASP.NET Core 3.0 and later includes an analyzer that issues compiler warnings if the type is being used directly.</span></span>
* <span data-ttu-id="a87df-108">`RenderTreeFrame` が直接参照される場合でも、この変更ではバイナリは中断させますが、ソースは中断させません。</span><span class="sxs-lookup"><span data-stu-id="a87df-108">Even if you reference `RenderTreeFrame` directly, this change is binary-breaking but not source-breaking.</span></span> <span data-ttu-id="a87df-109">つまり、既存のお使いのソース コードは正常にコンパイルされ、動作します。</span><span class="sxs-lookup"><span data-stu-id="a87df-109">That is, your existing source code will compile and behave properly.</span></span> <span data-ttu-id="a87df-110">.NET Core 3.x フレームワークに対してコンパイルされ、それらのバイナリが .NET 5.0 RC1 以降のフレームワークに対して実行される場合にのみ、問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="a87df-110">You'll only encounter an issue if compiling against a .NET Core 3.x framework and then running those binaries against the .NET 5.0 RC1 and later framework.</span></span>

<span data-ttu-id="a87df-111">ディスカッションについては、GitHub イシュー [dotnet/aspnetcore#25727](https://github.com/dotnet/aspnetcore/issues/25727) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a87df-111">For discussion, see GitHub issue [dotnet/aspnetcore#25727](https://github.com/dotnet/aspnetcore/issues/25727).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="a87df-112">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="a87df-112">Version introduced</span></span>

<span data-ttu-id="a87df-113">5.0 RC1</span><span class="sxs-lookup"><span data-stu-id="a87df-113">5.0 RC1</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="a87df-114">以前の動作</span><span class="sxs-lookup"><span data-stu-id="a87df-114">Old behavior</span></span>

<span data-ttu-id="a87df-115">`RenderTreeFrame` のパブリック メンバーはフィールドとして定義されていました。</span><span class="sxs-lookup"><span data-stu-id="a87df-115">Public members on `RenderTreeFrame` are defined as fields.</span></span> <span data-ttu-id="a87df-116">たとえば、`renderTreeFrame.Sequence` や `renderTreeFrame.ElementName`す。</span><span class="sxs-lookup"><span data-stu-id="a87df-116">For example, `renderTreeFrame.Sequence` and `renderTreeFrame.ElementName`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="a87df-117">新しい動作</span><span class="sxs-lookup"><span data-stu-id="a87df-117">New behavior</span></span>

<span data-ttu-id="a87df-118">`RenderTreeFrame` のパブリック メンバーは、以前と同じ名前でプロパティとして定義されます。</span><span class="sxs-lookup"><span data-stu-id="a87df-118">Public members on `RenderTreeFrame` are defined as properties with the same names as before.</span></span> <span data-ttu-id="a87df-119">たとえば、`renderTreeFrame.Sequence` や `renderTreeFrame.ElementName`す。</span><span class="sxs-lookup"><span data-stu-id="a87df-119">For example, `renderTreeFrame.Sequence` and `renderTreeFrame.ElementName`.</span></span>

<span data-ttu-id="a87df-120">この変更以降、以前のプリコンパイル済みのコードが再コンパイルされていない場合、*MissingFieldException:フィールドが見つかりません:'Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.FrameType'* のような例外がスローされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a87df-120">If older precompiled code hasn't been recompiled since this change, it may throw an exception similar to *MissingFieldException: Field not found: 'Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.FrameType'*.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="a87df-121">変更理由</span><span class="sxs-lookup"><span data-stu-id="a87df-121">Reason for change</span></span>

<span data-ttu-id="a87df-122">この変更は、ASP.NET Core 5.0 でレンダリングされる Blazor コンポーネントに影響力の大きいパフォーマンス向上を実装するために必要でした。</span><span class="sxs-lookup"><span data-stu-id="a87df-122">This change was necessary to implement high-impact performance improvements in Blazor component rendering in ASP.NET Core 5.0.</span></span> <span data-ttu-id="a87df-123">安全性とカプセル化については、同じレベルが維持されています。</span><span class="sxs-lookup"><span data-stu-id="a87df-123">The same levels of safety and encapsulation are maintained.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a87df-124">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="a87df-124">Recommended action</span></span>

<span data-ttu-id="a87df-125">多くの Blazor 開発者は、この変更の影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="a87df-125">Most Blazor developers are unaffected by this change.</span></span> <span data-ttu-id="a87df-126">変更の影響は、ライブラリ作成者とパッケージ作成者の方が受ける可能性は高いですが、まれなケースにおいてです。</span><span class="sxs-lookup"><span data-stu-id="a87df-126">The change is more likely to affect library and package authors, but only in rare cases.</span></span> <span data-ttu-id="a87df-127">具体的には、次のように開発している場合です。</span><span class="sxs-lookup"><span data-stu-id="a87df-127">Specifically, if you're developing:</span></span>

* <span data-ttu-id="a87df-128">アプリを開発していて、ASP.NET Core 3.x を使用するか、5.0 RC1 以降にアップグレードする場合は、自分自身のコードを変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a87df-128">An app and using ASP.NET Core 3.x or upgrading to 5.0 RC1 or later, you don't need to change your own code.</span></span> <span data-ttu-id="a87df-129">ただし、依存しているライブラリをこの変更に対応するためにアップグレードした場合は、そのライブラリを新しいバージョンに更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a87df-129">However, if you depend on a library that upgraded to account for this change, then you need to update to a newer version of that library.</span></span>
* <span data-ttu-id="a87df-130">ライブラリを開発していて、ASP.NET Core 5.0 RC1 以降のみをサポートするようにしたい場合は、何もする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a87df-130">A library and want to support only ASP.NET Core 5.0 RC1 or later, no action is needed.</span></span> <span data-ttu-id="a87df-131">お使いのプロジェクト ファイルで、`net5.0` 以降のバージョンの `<TargetFramework>` 値は宣言するようにします。</span><span class="sxs-lookup"><span data-stu-id="a87df-131">Just ensure that your project file declares a `<TargetFramework>` value of `net5.0` or a later version.</span></span>
* <span data-ttu-id="a87df-132">ライブラリを開発していて、ASP.NET Core 3.x *と* 5.0 の両方をサポートする場合、自分のコードで `RenderTreeFrame` メンバーを読み取るか判断します。</span><span class="sxs-lookup"><span data-stu-id="a87df-132">A library and want to support both ASP.NET Core 3.x *and* 5.0, determine whether your code reads any `RenderTreeFrame` members.</span></span> <span data-ttu-id="a87df-133">たとえば、`someRenderTreeFrame.FrameType` を評価するかです。</span><span class="sxs-lookup"><span data-stu-id="a87df-133">For example, evaluating `someRenderTreeFrame.FrameType`.</span></span>
  * <span data-ttu-id="a87df-134">多くのライブラリでは、`.razor` コンポーネントを含むライブラリを含む `RenderTreeFrame` メンバーは読み取りません。</span><span class="sxs-lookup"><span data-stu-id="a87df-134">Most libraries won't read `RenderTreeFrame` members, including libraries that contain `.razor` components.</span></span> <span data-ttu-id="a87df-135">この場合、何もする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a87df-135">In this case, no action is needed.</span></span>
  * <span data-ttu-id="a87df-136">ただし、自分のライブラリでそれが行われる場合は、`netstandard2.1` と `net5.0` の両方をターゲットにしてサポートされるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a87df-136">However, if your library does that, you'll need to multi-target to support both `netstandard2.1` and `net5.0`.</span></span> <span data-ttu-id="a87df-137">お使いのプロジェクト ファイルを次のように変更します。</span><span class="sxs-lookup"><span data-stu-id="a87df-137">Apply the following changes in your project file:</span></span>
    * <span data-ttu-id="a87df-138">既存の `<TargetFramework>` 要素を `<TargetFrameworks>netstandard2.0;net5.0</TargetFrameworks>` に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="a87df-138">Replace the existing `<TargetFramework>` element with `<TargetFrameworks>netstandard2.0;net5.0</TargetFrameworks>`.</span></span>
    * <span data-ttu-id="a87df-139">サポートする両バージョンに対応できるよう、条件付き `Microsoft.AspNetCore.Components` パッケージ参照を使用します。</span><span class="sxs-lookup"><span data-stu-id="a87df-139">Use a conditional `Microsoft.AspNetCore.Components` package reference to account for both versions you wish to support.</span></span> <span data-ttu-id="a87df-140">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a87df-140">For example:</span></span>

        ```xml
        <PackageReference Include="Microsoft.AspNetCore.Components" Version="3.0.0" Condition="'$(TargetFramework)' == 'netstandard2.0'" />
        <PackageReference Include="Microsoft.AspNetCore.Components" Version="5.0.0-rc.1.*" Condition="'$(TargetFramework)' != 'netstandard2.0'" />
        ```

<span data-ttu-id="a87df-141">詳細については、[@jsakamoto が `Toolbelt.Blazor.HeadElement` ライブラリをどのようにアップグレードしたかの違いを示した](https://github.com/jsakamoto/Toolbelt.Blazor.HeadElement/commit/090df430ba725f9420d412753db8104e8c32bf51)ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a87df-141">For further clarification, see this [diff showing how @jsakamoto already upgraded the `Toolbelt.Blazor.HeadElement` library](https://github.com/jsakamoto/Toolbelt.Blazor.HeadElement/commit/090df430ba725f9420d412753db8104e8c32bf51).</span></span>

#### <a name="category"></a><span data-ttu-id="a87df-142">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="a87df-142">Category</span></span>

<span data-ttu-id="a87df-143">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="a87df-143">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a87df-144">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="a87df-144">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame`

-->
