---
title: 状態管理
description: ASP.NET Web Forms と Blazor で状態を管理するためのさまざまなアプローチについて説明します。
author: csharpfritz
ms.author: jefritz
ms.date: 05/15/2020
ms.openlocfilehash: bac2f00330113725f09259ca31bdf857a8769f24
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/11/2020
ms.locfileid: "88062341"
---
# <a name="state-management"></a><span data-ttu-id="6b4f8-103">状態管理</span><span class="sxs-lookup"><span data-stu-id="6b4f8-103">State management</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="6b4f8-104">状態管理は、ビューステート、セッション状態、アプリケーション状態、およびポストバック機能を使用して容易に行うことができ、Web フォームアプリケーションの重要な概念です。</span><span class="sxs-lookup"><span data-stu-id="6b4f8-104">State management is a key concept of Web Forms applications, facilitated through View State, Session State, Application State, and Postback features.</span></span> <span data-ttu-id="6b4f8-105">このフレームワークのステートフル機能は、アプリケーションに必要な状態管理を非表示にし、アプリケーション開発者が機能の提供に専念できるようにするために役立ちました。</span><span class="sxs-lookup"><span data-stu-id="6b4f8-105">These stateful features of the framework helped to hide the state management required for an application and allow application developers to focus on delivering their functionality.</span></span> <span data-ttu-id="6b4f8-106">ASP.NET Core と Blazor を使用すると、これらの機能の一部が再配置され、一部が完全に削除されました。</span><span class="sxs-lookup"><span data-stu-id="6b4f8-106">With ASP.NET Core and Blazor, some of these features have been relocated and some have been removed altogether.</span></span> <span data-ttu-id="6b4f8-107">この章では、Blazor の新機能を使用して、状態を維持し、同じ機能を提供する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6b4f8-107">This chapter reviews how to maintain state and deliver the same functionality with the new features in Blazor.</span></span>

## <a name="request-state-management-with-viewstate"></a><span data-ttu-id="6b4f8-108">ViewState を使用した状態管理の要求</span><span class="sxs-lookup"><span data-stu-id="6b4f8-108">Request state management with ViewState</span></span>

<span data-ttu-id="6b4f8-109">Web フォームアプリケーションで状態管理を説明する際には、多くの開発者が ViewState をすぐに考えます。</span><span class="sxs-lookup"><span data-stu-id="6b4f8-109">When discussing state management in Web Forms application, many developers will immediately think of ViewState.</span></span> <span data-ttu-id="6b4f8-110">Web フォームでは、ViewState は、大きなエンコードされたテキストブロックをブラウザーに送信することによって、HTTP 要求間のコンテンツの状態を管理します。</span><span class="sxs-lookup"><span data-stu-id="6b4f8-110">In Web Forms, ViewState manages the state of the content between HTTP requests by sending a large encoded block of text back and forth to the browser.</span></span> <span data-ttu-id="6b4f8-111">複数の要素を含むページのコンテンツが ViewState フィールドに格納され、サイズが数メガバイトに拡大する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6b4f8-111">The ViewState field could be overwhelmed with content from a page containing many elements, potentially expanding to several megabytes in size.</span></span>

<span data-ttu-id="6b4f8-112">Blazor Server では、アプリはサーバーとの継続的な接続を維持します。</span><span class="sxs-lookup"><span data-stu-id="6b4f8-112">With Blazor Server, the app maintains an ongoing connection with the server.</span></span> <span data-ttu-id="6b4f8-113">接続はアクティブと見なされますが、*回線*と呼ばれるアプリの状態はサーバーメモリに保持されます。</span><span class="sxs-lookup"><span data-stu-id="6b4f8-113">The app's state, called a *circuit*, is held in server memory while the connection is considered active.</span></span> <span data-ttu-id="6b4f8-114">状態は、ユーザーがアプリから移動したとき、またはアプリ内の特定のページに移動したときにのみ破棄されます。</span><span class="sxs-lookup"><span data-stu-id="6b4f8-114">State will only be disposed when the user navigates away from the app or a particular page in the app.</span></span> <span data-ttu-id="6b4f8-115">アクティブなコンポーネントのすべてのメンバーは、サーバーとのやり取りの間で使用できます。</span><span class="sxs-lookup"><span data-stu-id="6b4f8-115">All members of the active components are available between interactions with the server.</span></span>

<span data-ttu-id="6b4f8-116">この機能にはいくつかの利点があります。</span><span class="sxs-lookup"><span data-stu-id="6b4f8-116">There are several advantages of this feature:</span></span>

- <span data-ttu-id="6b4f8-117">コンポーネントの状態はすぐに使用でき、相互作用間で再構築されることはありません。</span><span class="sxs-lookup"><span data-stu-id="6b4f8-117">Component state is readily available and not rebuilt between interactions.</span></span>
- <span data-ttu-id="6b4f8-118">状態はブラウザーに送信されません。</span><span class="sxs-lookup"><span data-stu-id="6b4f8-118">State isn't transmitted to the browser.</span></span>

<span data-ttu-id="6b4f8-119">ただし、メモリ内コンポーネントの状態の永続化にはいくつかの欠点があります。</span><span class="sxs-lookup"><span data-stu-id="6b4f8-119">However, there are some disadvantages to in-memory component state persistence to be aware of:</span></span>

- <span data-ttu-id="6b4f8-120">サーバーが要求の間で再起動した場合、状態は失われます。</span><span class="sxs-lookup"><span data-stu-id="6b4f8-120">If the server restarts between request, state is lost.</span></span>
- <span data-ttu-id="6b4f8-121">アプリケーション web サーバーの負荷分散ソリューションには、同じブラウザーからのすべての要求が同じサーバーに返されるようにするために、固定セッションが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b4f8-121">Your application web server load-balancing solution must include sticky sessions to ensure that all requests from the same browser return to the same server.</span></span> <span data-ttu-id="6b4f8-122">要求が別のサーバーに送信されると、状態は失われます。</span><span class="sxs-lookup"><span data-stu-id="6b4f8-122">If a request goes to a different server, state will be lost.</span></span>
- <span data-ttu-id="6b4f8-123">サーバー上のコンポーネントの状態が永続化されると、web サーバーのメモリ負荷が低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6b4f8-123">Persistence of component state on the server can lead to memory pressure on the web server.</span></span>

<span data-ttu-id="6b4f8-124">上記の理由から、コンポーネントの状態だけを使用して、サーバー上のメモリ内に常駐させることは避けてください。</span><span class="sxs-lookup"><span data-stu-id="6b4f8-124">For the preceding reasons, don't rely on just the state of the component to reside in-memory on the server.</span></span> <span data-ttu-id="6b4f8-125">アプリケーションには、要求間のデータのバッキングデータストアも含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b4f8-125">Your application should also include some backing data store for data between requests.</span></span> <span data-ttu-id="6b4f8-126">この戦略の簡単な例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6b4f8-126">Some simple examples of this strategy:</span></span>

- <span data-ttu-id="6b4f8-127">ショッピングカートアプリケーションでは、カートに追加された新しいアイテムの内容をデータベースレコードに保持します。</span><span class="sxs-lookup"><span data-stu-id="6b4f8-127">In a shopping cart application, persist the content of new items added to the cart in a database record.</span></span> <span data-ttu-id="6b4f8-128">サーバーの状態が失われた場合は、データベースレコードから再構築できます。</span><span class="sxs-lookup"><span data-stu-id="6b4f8-128">If the state on the server is lost, you can reconstitute it from the database records.</span></span>
- <span data-ttu-id="6b4f8-129">マルチパート web フォームでは、ユーザーは各要求の間の値を記憶する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b4f8-129">In a multi-part web form, your users will expect your application to remember values between each request.</span></span> <span data-ttu-id="6b4f8-130">複数の部分から構成されるフォームが完成したときに、ユーザーの各投稿の間でデータをフェッチして最終的な形式の応答構造にアセンブルできるように、データストアにデータを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="6b4f8-130">Write the data between each of your user's posts to a data store so that they can be fetched and assembled into the final form response structure when the multi-part form is completed.</span></span>

<span data-ttu-id="6b4f8-131">Blazor アプリでの状態の管理の詳細については、「 [ASP.NET Core Blazor state management](/aspnet/core/blazor/state-management)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b4f8-131">For additional details on managing state in Blazor apps, see [ASP.NET Core Blazor state management](/aspnet/core/blazor/state-management).</span></span>

## <a name="maintain-state-with-session"></a><span data-ttu-id="6b4f8-132">セッションで状態を維持する</span><span class="sxs-lookup"><span data-stu-id="6b4f8-132">Maintain state with Session</span></span>

<span data-ttu-id="6b4f8-133">Web フォーム開発者は、dictionary オブジェクトを使用して現在動作しているユーザーに関する情報を保持でき <xref:Microsoft.AspNetCore.Http.ISession?displayProperty=nameWithType> ます。</span><span class="sxs-lookup"><span data-stu-id="6b4f8-133">Web Forms developers could maintain information about the currently acting user with the <xref:Microsoft.AspNetCore.Http.ISession?displayProperty=nameWithType> dictionary object.</span></span> <span data-ttu-id="6b4f8-134">文字列キーを持つオブジェクトをに追加するのは簡単です。このオブジェクトは、ユーザーがアプリケーションと対話するときに後で使用できるようになり `Session` ます。</span><span class="sxs-lookup"><span data-stu-id="6b4f8-134">It's easy enough to add an object with a string key to the `Session`, and that object would be available at a later time during the user's interactions with the application.</span></span> <span data-ttu-id="6b4f8-135">HTTP との対話を管理しないようにするために、 `Session` オブジェクトは状態を簡単に維持できるようにしました。</span><span class="sxs-lookup"><span data-stu-id="6b4f8-135">In an attempt to eliminate managing interacting with HTTP, the `Session` object made it easy to maintain state.</span></span>

<span data-ttu-id="6b4f8-136">.NET Framework オブジェクトのシグネチャが `Session` ASP.NET Core オブジェクトと同じではありません `Session` 。</span><span class="sxs-lookup"><span data-stu-id="6b4f8-136">The signature of the .NET Framework `Session` object isn't the same as the ASP.NET Core `Session` object.</span></span> <span data-ttu-id="6b4f8-137">新しいセッション状態機能の移行と使用を決定する前に、[新しい ASP.NET Core セッションのドキュメント](/dotnet/api/microsoft.aspnetcore.http.isession)を検討してください。</span><span class="sxs-lookup"><span data-stu-id="6b4f8-137">Consider [the documentation for the new ASP.NET Core Session](/dotnet/api/microsoft.aspnetcore.http.isession) before deciding to migrate and use the new session state feature.</span></span>

<span data-ttu-id="6b4f8-138">セッションは ASP.NET Core および Blazor サーバーで使用できますが、データを適切にデータリポジトリに格納することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6b4f8-138">Session is available in ASP.NET Core and Blazor Server, but is discouraged from use in favor of storing data in a data repository appropriately.</span></span> <span data-ttu-id="6b4f8-139">また、プライバシーの問題により、ユーザーがアプリケーションで HTTP cookie の使用を拒否した場合も、セッション状態は機能しません。</span><span class="sxs-lookup"><span data-stu-id="6b4f8-139">Session state is also not functional if visitors decline the use HTTP cookies in your application due to privacy concerns.</span></span>

<span data-ttu-id="6b4f8-140">ASP.NET Core とセッション状態の構成については[ASP.NET Core のセッションと状態の管理](/aspnet/core/fundamentals/app-state#session-state)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b4f8-140">Configuration for ASP.NET Core and Session state is available in the [Session and state management in ASP.NET Core article](/aspnet/core/fundamentals/app-state#session-state).</span></span>

## <a name="application-state"></a><span data-ttu-id="6b4f8-141">アプリケーションの状態</span><span class="sxs-lookup"><span data-stu-id="6b4f8-141">Application state</span></span>

<span data-ttu-id="6b4f8-142">`Application`Web フォームフレームワークのオブジェクトには、アプリケーションスコープの構成と状態を操作するための、大量の要求のないリポジトリが用意されています。</span><span class="sxs-lookup"><span data-stu-id="6b4f8-142">The `Application` object in the Web Forms framework provides a massive, cross-request repository for interacting with application-scope configuration and state.</span></span> <span data-ttu-id="6b4f8-143">アプリケーションの状態は、要求を行ったユーザーに関係なく、すべての要求で参照されるさまざまなアプリケーション構成プロパティを格納するための理想的な場所です。</span><span class="sxs-lookup"><span data-stu-id="6b4f8-143">Application state was an ideal place to store various application configuration properties that would be referenced by all requests, regardless of the user making the request.</span></span> <span data-ttu-id="6b4f8-144">オブジェクトの問題は、 `Application` データが複数のサーバーにわたって保持されていないということでした。</span><span class="sxs-lookup"><span data-stu-id="6b4f8-144">The problem with the `Application` object was that data didn't persist across multiple servers.</span></span> <span data-ttu-id="6b4f8-145">再起動の間にアプリケーションオブジェクトの状態が失われました。</span><span class="sxs-lookup"><span data-stu-id="6b4f8-145">The state of the application object was lost between restarts.</span></span>

<span data-ttu-id="6b4f8-146">と同様に `Session` 、複数のサーバーインスタンスからアクセスできる永続的なバッキングストアにデータを移動することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6b4f8-146">As with `Session`, it's recommended that data move to a persistent backing store that could be accessed by multiple server instances.</span></span> <span data-ttu-id="6b4f8-147">要求とユーザー間でアクセスできるようにする揮発性のデータがある場合は、この情報または操作を必要とするコンポーネントに挿入できるシングルトンサービスにデータを簡単に格納できます。</span><span class="sxs-lookup"><span data-stu-id="6b4f8-147">If there is volatile data that you would like to be able to access across requests and users, you could easily store it in a singleton service that can be injected into components that require this information or interaction.</span></span>

<span data-ttu-id="6b4f8-148">アプリケーションの状態とその消費を維持するためのオブジェクトの構築は、次のような実装になります。</span><span class="sxs-lookup"><span data-stu-id="6b4f8-148">The construction of an object to maintain application state and its consumption could resemble the following implementation:</span></span>

```csharp
public class MyApplicationState
{
    public int VisitorCounter { get; private set; } = 0;

    public void IncrementCounter() => VisitorCounter += 1;
}
```

```csharp
app.AddSingleton<MyApplicationState>();
```

```razor
@inject MyApplicationState AppState

<label>Total Visitors: @AppState.VisitorCounter</label>
```

<span data-ttu-id="6b4f8-149">`MyApplicationState`オブジェクトはサーバーに1回だけ作成され、値 `VisitorCounter` がフェッチされてコンポーネントのラベルに出力されます。</span><span class="sxs-lookup"><span data-stu-id="6b4f8-149">The `MyApplicationState` object is created only once on the server, and the value `VisitorCounter` is fetched and output in the component's label.</span></span> <span data-ttu-id="6b4f8-150">`VisitorCounter`持続性とスケーラビリティを確保するために、値は保持され、バッキングデータストアから取得される必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b4f8-150">The `VisitorCounter` value should be persisted and retrieved from a backing data store for durability and scalability.</span></span>

## <a name="in-the-browser"></a><span data-ttu-id="6b4f8-151">ブラウザーで</span><span class="sxs-lookup"><span data-stu-id="6b4f8-151">In the browser</span></span>

<span data-ttu-id="6b4f8-152">アプリケーションデータは、ユーザーのデバイスにクライアント側で格納して、後で使用できるようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="6b4f8-152">Application data can also be stored client-side on the user's device so that is available later.</span></span> <span data-ttu-id="6b4f8-153">ユーザーのブラウザーの異なるスコープのデータを永続化できるブラウザー機能が2つあります。</span><span class="sxs-lookup"><span data-stu-id="6b4f8-153">There are two browser features that allow for persistence of data in different scopes of the user's browser:</span></span>

- <span data-ttu-id="6b4f8-154">`localStorage`-ユーザーのブラウザー全体に適用されます。</span><span class="sxs-lookup"><span data-stu-id="6b4f8-154">`localStorage` - scoped to the user's entire browser.</span></span> <span data-ttu-id="6b4f8-155">ページが再読み込みされると、ブラウザーが閉じて再度開かれます。または、同じ URL で別のタブが開かれている場合は、 `localStorage` ブラウザーによっても表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b4f8-155">If the page is reloaded, the browser is closed and reopened, or another tab is opened with the same URL then the same `localStorage` is provided by the browser</span></span>
- <span data-ttu-id="6b4f8-156">`sessionStorage`-ユーザーの現在のブラウザータブを対象とします。タブが再度読み込まれた場合は、状態が維持されます。</span><span class="sxs-lookup"><span data-stu-id="6b4f8-156">`sessionStorage` - scoped to the user's current browser tab. If the tab is reloaded, the state persists.</span></span> <span data-ttu-id="6b4f8-157">ただし、ユーザーがアプリケーションに対して別のタブを開くか、ブラウザーを閉じてから再度開くと、状態は失われます。</span><span class="sxs-lookup"><span data-stu-id="6b4f8-157">However, if the user opens another tab to your application or closes and reopens the browser the state is lost.</span></span>

<span data-ttu-id="6b4f8-158">これらの機能を操作するためのカスタム JavaScript コードを記述することも、この機能を提供するいくつかの NuGet パッケージを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="6b4f8-158">You can write some custom JavaScript code to interact with these features, or there are a number of NuGet packages that you can use that provide this functionality.</span></span> <span data-ttu-id="6b4f8-159">このようなパッケージの1つは、 [AspNetCore. ProtectedBrowserStorage](https://www.nuget.org/packages/Microsoft.AspNetCore.ProtectedBrowserStorage)です。</span><span class="sxs-lookup"><span data-stu-id="6b4f8-159">One such package is [Microsoft.AspNetCore.ProtectedBrowserStorage](https://www.nuget.org/packages/Microsoft.AspNetCore.ProtectedBrowserStorage).</span></span>

<span data-ttu-id="6b4f8-160">このパッケージを使用してとを操作する方法については `localStorage` `sessionStorage` 、 [Blazor 状態管理](/aspnet/core/blazor/state-management#protected-browser-storage-experimental-package)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b4f8-160">For instructions on utilizing this package to interact with `localStorage` and `sessionStorage`, see the [Blazor State Management](/aspnet/core/blazor/state-management#protected-browser-storage-experimental-package) article.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="6b4f8-161">[前へ](pages-routing-layouts.md)
>[次へ](forms-validation.md)</span><span class="sxs-lookup"><span data-stu-id="6b4f8-161">[Previous](pages-routing-layouts.md)
[Next](forms-validation.md)</span></span>
