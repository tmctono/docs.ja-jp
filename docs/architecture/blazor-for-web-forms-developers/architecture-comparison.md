---
title: ASP.NET Web フォームとのアーキテクチャの比較Blazor
description: ASP.NET Web フォームと比較のアーキテクチャについて説明し Blazor ます。
author: danroth27
ms.author: daroth
no-loc:
- Blazor
ms.date: 09/11/2019
ms.openlocfilehash: 51b114c842e131ad9b9a589bf5137a522e135082
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2020
ms.locfileid: "86173433"
---
# <a name="architecture-comparison-of-aspnet-web-forms-and-blazor"></a><span data-ttu-id="d8e1a-103">ASP.NET Web フォームとのアーキテクチャの比較Blazor</span><span class="sxs-lookup"><span data-stu-id="d8e1a-103">Architecture comparison of ASP.NET Web Forms and Blazor</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="d8e1a-104">ASP.NET の Web フォームとには Blazor 多くの類似した概念がありますが、そのしくみには違いがあります。</span><span class="sxs-lookup"><span data-stu-id="d8e1a-104">While ASP.NET Web Forms and Blazor have many similar concepts, there are differences in how they work.</span></span> <span data-ttu-id="d8e1a-105">この章では、ASP.NET Web フォームとの内部の動作とアーキテクチャについて説明し Blazor ます。</span><span class="sxs-lookup"><span data-stu-id="d8e1a-105">This chapter examines the inner workings and architectures of ASP.NET Web Forms and Blazor.</span></span>

## <a name="aspnet-web-forms"></a><span data-ttu-id="d8e1a-106">ASP.NET Web Forms</span><span class="sxs-lookup"><span data-stu-id="d8e1a-106">ASP.NET Web Forms</span></span>

<span data-ttu-id="d8e1a-107">ASP.NET Web Forms framework は、ページ中心のアーキテクチャに基づいています。</span><span class="sxs-lookup"><span data-stu-id="d8e1a-107">The ASP.NET Web Forms framework is based on a page-centric architecture.</span></span> <span data-ttu-id="d8e1a-108">アプリ内の場所に対する各 HTTP 要求は、ASP.NET が応答する別のページです。</span><span class="sxs-lookup"><span data-stu-id="d8e1a-108">Each HTTP request for a location in the app is a separate page with which ASP.NET responds.</span></span> <span data-ttu-id="d8e1a-109">ページが要求されると、ブラウザーのコンテンツは要求されたページの結果に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="d8e1a-109">As pages are requested, the contents of the browser are replaced with the results of the page requested.</span></span>

<span data-ttu-id="d8e1a-110">ページは次のコンポーネントで構成されています。</span><span class="sxs-lookup"><span data-stu-id="d8e1a-110">Pages consist of the following components:</span></span>

- <span data-ttu-id="d8e1a-111">HTML マークアップ</span><span class="sxs-lookup"><span data-stu-id="d8e1a-111">HTML markup</span></span>
- <span data-ttu-id="d8e1a-112">C# または Visual Basic コード</span><span class="sxs-lookup"><span data-stu-id="d8e1a-112">C# or Visual Basic code</span></span>
- <span data-ttu-id="d8e1a-113">ロジックおよびイベント処理機能を含む分離コードクラス</span><span class="sxs-lookup"><span data-stu-id="d8e1a-113">A code-behind class containing logic and event-handling capabilities</span></span>
- <span data-ttu-id="d8e1a-114">コントロール</span><span class="sxs-lookup"><span data-stu-id="d8e1a-114">Controls</span></span>

<span data-ttu-id="d8e1a-115">コントロールは、ページ上でプログラムによって配置および操作できる web UI の再利用可能な単位です。</span><span class="sxs-lookup"><span data-stu-id="d8e1a-115">Controls are reusable units of web UI that can be programmatically placed and interacted with on a page.</span></span> <span data-ttu-id="d8e1a-116">ページは、マークアップ、コントロール、および一部のコードを含む *.aspx*で終わるファイルで構成されます。</span><span class="sxs-lookup"><span data-stu-id="d8e1a-116">Pages are composed of files that end with *.aspx* containing markup, controls, and some code.</span></span> <span data-ttu-id="d8e1a-117">分離コードクラスは、使用するプログラミング言語に応じて、同じ基本名と*aspx.cs*または *.aspx*拡張子を持つファイルにあります。</span><span class="sxs-lookup"><span data-stu-id="d8e1a-117">The code-behind classes are in files with the same base name and an *.aspx.cs* or *.aspx.vb* extension, depending on the programming language used.</span></span> <span data-ttu-id="d8e1a-118">興味深いことに、web サーバーは .aspx ファイルの内容を解釈し、変更されるたびにコンパイルし*ます*。</span><span class="sxs-lookup"><span data-stu-id="d8e1a-118">Interestingly, the web server interprets contents of the *.aspx* files and compiles them whenever they change.</span></span> <span data-ttu-id="d8e1a-119">この再コンパイルは、web サーバーが既に実行されている場合でも発生します。</span><span class="sxs-lookup"><span data-stu-id="d8e1a-119">This recompilation occurs even if the web server is already running.</span></span>

<span data-ttu-id="d8e1a-120">コントロールは、マークアップを使用して作成し、ユーザーコントロールとして配信できます。</span><span class="sxs-lookup"><span data-stu-id="d8e1a-120">Controls can be built with markup and delivered as user controls.</span></span> <span data-ttu-id="d8e1a-121">ユーザーコントロールはクラスから派生 `UserControl` し、ページと同様の構造を持ちます。</span><span class="sxs-lookup"><span data-stu-id="d8e1a-121">A user control derives from the `UserControl` class and has a similar structure to the Page.</span></span> <span data-ttu-id="d8e1a-122">ユーザーコントロールのマークアップは *.ascx*ファイルに格納されます。</span><span class="sxs-lookup"><span data-stu-id="d8e1a-122">Markup for user controls is stored in an *.ascx* file.</span></span> <span data-ttu-id="d8e1a-123">付随する分離コードクラスは、 *ascx.cs*ファイルまたは *.ascx*ファイルに存在します。</span><span class="sxs-lookup"><span data-stu-id="d8e1a-123">An accompanying code-behind class resides in an *.ascx.cs* or *.ascx.vb* file.</span></span> <span data-ttu-id="d8e1a-124">コントロールは、またはの基底クラスから継承することにより、コードを使用して完全にビルドすることもでき `WebControl` `CompositeControl` ます。</span><span class="sxs-lookup"><span data-stu-id="d8e1a-124">Controls can also be built completely with code, by inheriting from either the `WebControl` or `CompositeControl` base class.</span></span>

<span data-ttu-id="d8e1a-125">ページには、広範なイベントライフサイクルもあります。</span><span class="sxs-lookup"><span data-stu-id="d8e1a-125">Pages also have an extensive event lifecycle.</span></span> <span data-ttu-id="d8e1a-126">各ページは、ASP.NET ランタイムが各要求に対してページのコードを実行するときに発生する、初期化、読み込み、prerender、およびアンロードイベントに対してイベントを発生させます。</span><span class="sxs-lookup"><span data-stu-id="d8e1a-126">Each page raises events for the initialization, load, prerender, and unload events that occur as the ASP.NET runtime executes the page's code for each request.</span></span>

<span data-ttu-id="d8e1a-127">通常、ページ上のコントロールは、コントロールが表示されるのと同じページにポストバックされ、という名前の非表示フィールドからのペイロードと共に使用され `ViewState` ます。</span><span class="sxs-lookup"><span data-stu-id="d8e1a-127">Controls on a Page typically post-back to the same page that presented the control, and carry along with them a payload from a hidden form field called `ViewState`.</span></span> <span data-ttu-id="d8e1a-128">フィールドには、 `ViewState` コントロールがページに表示されて表示されるときのコントロールの状態に関する情報が含まれています。これにより、ASP.NET ランタイムは、サーバーに送信されたコンテンツの変更を比較および識別できます。</span><span class="sxs-lookup"><span data-stu-id="d8e1a-128">The `ViewState` field contains information about the state of the controls at the time they were rendered and presented on the page, allowing the ASP.NET runtime to compare and identify changes in the content submitted to the server.</span></span>

## Blazor

Blazor<span data-ttu-id="d8e1a-129">は、クライアント側の web UI フレームワークであり、角度や反応などの JavaScript フロントエンドフレームワークに似ています。</span><span class="sxs-lookup"><span data-stu-id="d8e1a-129"> is a client-side web UI framework similar in nature to JavaScript front-end frameworks like Angular or React.</span></span> Blazor<span data-ttu-id="d8e1a-130">ユーザー操作を処理し、必要な UI 更新をレンダリングします。</span><span class="sxs-lookup"><span data-stu-id="d8e1a-130"> handles user interactions and renders the necessary UI updates.</span></span> Blazor<span data-ttu-id="d8e1a-131">は、要求/応答モデルに基づいてい*ませ*ん。</span><span class="sxs-lookup"><span data-stu-id="d8e1a-131"> *isn't* based on a request-reply model.</span></span> <span data-ttu-id="d8e1a-132">ユーザー操作は、特定の HTTP 要求のコンテキストに含まれていないイベントとして処理されます。</span><span class="sxs-lookup"><span data-stu-id="d8e1a-132">User interactions are handled as events that aren't in the context of any particular HTTP request.</span></span>

Blazor<span data-ttu-id="d8e1a-133">アプリは、HTML ページにレンダリングされる1つ以上のルートコンポーネントで構成されます。</span><span class="sxs-lookup"><span data-stu-id="d8e1a-133"> apps consist of one or more root components that are rendered on an HTML page.</span></span>

<span data-ttu-id="d8e1a-134">![BlazorHTML のコンポーネント](./media/architecture-comparison/blazor-components-in-html.png)</span><span class="sxs-lookup"><span data-stu-id="d8e1a-134">![Blazor components in HTML](./media/architecture-comparison/blazor-components-in-html.png)</span></span>

<span data-ttu-id="d8e1a-135">ユーザーがコンポーネントを表示する場所を指定する方法と、ユーザーの操作のためにコンポーネントを接続する方法は、モデル固有の[ホスト](hosting-models.md)となります。</span><span class="sxs-lookup"><span data-stu-id="d8e1a-135">How the user specifies where components should render and how the components are then wired up for user interactions is [hosting model](hosting-models.md) specific.</span></span>

Blazor<span data-ttu-id="d8e1a-136">[コンポーネント](components.md)は、再利用可能な UI を表す .net クラスです。</span><span class="sxs-lookup"><span data-stu-id="d8e1a-136"> [components](components.md) are .NET classes that represent a reusable piece of UI.</span></span> <span data-ttu-id="d8e1a-137">各コンポーネントは、独自の状態を保持し、独自のレンダリングロジックを指定します。これには、他のコンポーネントのレンダリングを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="d8e1a-137">Each component maintains its own state and specifies its own rendering logic, which can include rendering other components.</span></span> <span data-ttu-id="d8e1a-138">コンポーネントは、コンポーネントの状態を更新するために、特定のユーザー操作のイベントハンドラーを指定します。</span><span class="sxs-lookup"><span data-stu-id="d8e1a-138">Components specify event handlers for specific user interactions to update the component's state.</span></span>

<span data-ttu-id="d8e1a-139">コンポーネントがイベントを処理した後、は Blazor コンポーネントをレンダリングし、レンダリングされた出力の変更内容を追跡します。</span><span class="sxs-lookup"><span data-stu-id="d8e1a-139">After a component handles an event, Blazor renders the component and keeps track of what changed in the rendered output.</span></span> <span data-ttu-id="d8e1a-140">コンポーネントは、ドキュメントオブジェクトモデル (DOM) に直接はレンダリングされません。</span><span class="sxs-lookup"><span data-stu-id="d8e1a-140">Components don't render directly to the Document Object Model (DOM).</span></span> <span data-ttu-id="d8e1a-141">代わりに、は、変更を追跡できるように、と呼ばれる DOM のメモリ内表現にレンダリングし `RenderTree` Blazor ます。</span><span class="sxs-lookup"><span data-stu-id="d8e1a-141">They instead render to an in-memory representation of the DOM called a `RenderTree` so that Blazor can track the changes.</span></span> Blazor<span data-ttu-id="d8e1a-142">新しくレンダリングされた出力を前の出力と比較して、UI の相違を計算します。これにより、DOM に効率よく適用されます。</span><span class="sxs-lookup"><span data-stu-id="d8e1a-142"> compares the newly rendered output with the previous output to calculate a UI diff that it then applies efficiently to the DOM.</span></span>

<span data-ttu-id="d8e1a-143">![BlazorDOM の相互作用](./media/architecture-comparison/blazor-dom-interaction.png)</span><span class="sxs-lookup"><span data-stu-id="d8e1a-143">![Blazor DOM interaction](./media/architecture-comparison/blazor-dom-interaction.png)</span></span>

<span data-ttu-id="d8e1a-144">また、コンポーネントの状態が通常の UI イベントの外部で変更された場合に、それらのコンポーネントがレンダリングされることを手動で示すこともできます。</span><span class="sxs-lookup"><span data-stu-id="d8e1a-144">Components can also manually indicate that they should be rendered if their state changes outside of a normal UI event.</span></span> Blazor<span data-ttu-id="d8e1a-145"> では、`SynchronizationContext` を使用して、1 つの論理スレッドを強制的に実行します。</span><span class="sxs-lookup"><span data-stu-id="d8e1a-145"> uses a `SynchronizationContext` to enforce a single logical thread of execution.</span></span> <span data-ttu-id="d8e1a-146">コンポーネントの ライフサイクル メソッドと Blazor によって発生するイベント コールバックは、この `SynchronizationContext` で実行されます。</span><span class="sxs-lookup"><span data-stu-id="d8e1a-146">A component's lifecycle methods and any event callbacks that are raised by Blazor are executed on this `SynchronizationContext`.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="d8e1a-147">[前へ](introduction.md)
>[次へ](hosting-models.md)</span><span class="sxs-lookup"><span data-stu-id="d8e1a-147">[Previous](introduction.md)
[Next](hosting-models.md)</span></span>
