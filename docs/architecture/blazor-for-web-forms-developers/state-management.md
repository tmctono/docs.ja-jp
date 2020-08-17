---
title: 状態管理
description: ASP.NET Web Forms と Blazor で状態を管理するためのさまざまなアプローチについて説明します。
author: csharpfritz
ms.author: jefritz
ms.date: 05/15/2020
ms.openlocfilehash: 2ca811f886c6a245ac16c2bd66a68ff16e5bfc44
ms.sourcegitcommit: 0100be20fcf23f61dab672deced70059ed71bb2e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/17/2020
ms.locfileid: "88267725"
---
# <a name="state-management"></a>状態管理

状態管理は、ビューステート、セッション状態、アプリケーション状態、およびポストバック機能を使用して容易に行うことができ、Web フォームアプリケーションの重要な概念です。 このフレームワークのステートフル機能は、アプリケーションに必要な状態管理を非表示にし、アプリケーション開発者が機能の提供に専念できるようにするために役立ちました。 ASP.NET Core と Blazor を使用すると、これらの機能の一部が再配置され、一部が完全に削除されました。 この章では、Blazor の新機能を使用して、状態を維持し、同じ機能を提供する方法について説明します。

## <a name="request-state-management-with-viewstate"></a>ViewState を使用した状態管理の要求

Web フォームアプリケーションで状態管理を説明する際には、多くの開発者が ViewState をすぐに考えます。 Web フォームでは、ViewState は、大きなエンコードされたテキストブロックをブラウザーに送信することによって、HTTP 要求間のコンテンツの状態を管理します。 複数の要素を含むページのコンテンツが ViewState フィールドに格納され、サイズが数メガバイトに拡大する可能性があります。

Blazor Server では、アプリはサーバーとの継続的な接続を維持します。 接続はアクティブと見なされますが、 *回線*と呼ばれるアプリの状態はサーバーメモリに保持されます。 状態は、ユーザーがアプリから移動したとき、またはアプリ内の特定のページに移動したときにのみ破棄されます。 アクティブなコンポーネントのすべてのメンバーは、サーバーとのやり取りの間で使用できます。

この機能にはいくつかの利点があります。

- コンポーネントの状態はすぐに使用でき、相互作用間で再構築されることはありません。
- 状態はブラウザーに送信されません。

ただし、メモリ内コンポーネントの状態の永続化にはいくつかの欠点があります。

- サーバーが要求の間で再起動した場合、状態は失われます。
- アプリケーション web サーバーの負荷分散ソリューションには、同じブラウザーからのすべての要求が同じサーバーに返されるようにするために、固定セッションが含まれている必要があります。 要求が別のサーバーに送信されると、状態は失われます。
- サーバー上のコンポーネントの状態が永続化されると、web サーバーのメモリ負荷が低下する可能性があります。

上記の理由から、コンポーネントの状態だけを使用して、サーバー上のメモリ内に常駐させることは避けてください。 アプリケーションには、要求間のデータのバッキングデータストアも含まれている必要があります。 この戦略の簡単な例を次に示します。

- ショッピングカートアプリケーションでは、カートに追加された新しいアイテムの内容をデータベースレコードに保持します。 サーバーの状態が失われた場合は、データベースレコードから再構築できます。
- マルチパート web フォームでは、ユーザーは各要求の間の値を記憶する必要があります。 複数の部分から構成されるフォームが完成したときに、ユーザーの各投稿の間でデータをフェッチして最終的な形式の応答構造にアセンブルできるように、データストアにデータを書き込みます。

Blazor アプリでの状態の管理の詳細については、「 [ASP.NET Core Blazor state management](/aspnet/core/blazor/state-management)」を参照してください。

## <a name="maintain-state-with-session"></a>セッションで状態を維持する

Web フォーム開発者は、dictionary オブジェクトを使用して現在動作しているユーザーに関する情報を保持でき <xref:Microsoft.AspNetCore.Http.ISession?displayProperty=nameWithType> ます。 文字列キーを持つオブジェクトをに追加するのは簡単です。このオブジェクトは、ユーザーがアプリケーションと対話するときに後で使用できるようになり `Session` ます。 HTTP との対話を管理しないようにするために、 `Session` オブジェクトは状態を簡単に維持できるようにしました。

.NET Framework オブジェクトのシグネチャが `Session` ASP.NET Core オブジェクトと同じではありません `Session` 。 新しいセッション状態機能の移行と使用を決定する前に、 [新しい ASP.NET Core セッションのドキュメント](/dotnet/api/microsoft.aspnetcore.http.isession) を検討してください。

セッションは ASP.NET Core および Blazor サーバーで使用できますが、データを適切にデータリポジトリに格納することをお勧めします。 また、プライバシーの問題により、ユーザーがアプリケーションで HTTP cookie の使用を拒否した場合も、セッション状態は機能しません。

ASP.NET Core とセッション状態の構成については [ASP.NET Core のセッションと状態の管理](/aspnet/core/fundamentals/app-state#session-state)」を参照してください。

## <a name="application-state"></a>アプリケーションの状態

`Application`Web フォームフレームワークのオブジェクトには、アプリケーションスコープの構成と状態を操作するための、大量の要求のないリポジトリが用意されています。 アプリケーションの状態は、要求を行ったユーザーに関係なく、すべての要求で参照されるさまざまなアプリケーション構成プロパティを格納するための理想的な場所です。 オブジェクトの問題は、 `Application` データが複数のサーバーにわたって保持されていないということでした。 再起動の間にアプリケーションオブジェクトの状態が失われました。

と同様に `Session` 、複数のサーバーインスタンスからアクセスできる永続的なバッキングストアにデータを移動することをお勧めします。 要求とユーザー間でアクセスできるようにする揮発性のデータがある場合は、この情報または操作を必要とするコンポーネントに挿入できるシングルトンサービスにデータを簡単に格納できます。

アプリケーションの状態とその消費を維持するためのオブジェクトの構築は、次のような実装になります。

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

`MyApplicationState`オブジェクトはサーバーに1回だけ作成され、値 `VisitorCounter` がフェッチされてコンポーネントのラベルに出力されます。 `VisitorCounter`持続性とスケーラビリティを確保するために、値は保持され、バッキングデータストアから取得される必要があります。

## <a name="in-the-browser"></a>ブラウザーで

アプリケーションデータは、ユーザーのデバイスにクライアント側で格納して、後で使用できるようにすることもできます。 ユーザーのブラウザーの異なるスコープのデータを永続化できるブラウザー機能が2つあります。

- `localStorage` -ユーザーのブラウザー全体に適用されます。 ページが再読み込みされると、ブラウザーが閉じて再度開かれます。または、同じ URL で別のタブが開かれている場合は、 `localStorage` ブラウザーによっても表示されます。
- `sessionStorage` -ユーザーの現在のブラウザータブを対象とします。タブが再度読み込まれた場合は、状態が維持されます。 ただし、ユーザーがアプリケーションに対して別のタブを開くか、ブラウザーを閉じてから再度開くと、状態は失われます。

これらの機能を操作するためのカスタム JavaScript コードを記述することも、この機能を提供するいくつかの NuGet パッケージを使用することもできます。 このようなパッケージの1つは、 [AspNetCore. ProtectedBrowserStorage](https://www.nuget.org/packages/Microsoft.AspNetCore.ProtectedBrowserStorage)です。

このパッケージを使用してとを操作する方法については `localStorage` `sessionStorage` 、 [Blazor 状態管理](/aspnet/core/blazor/state-management#protected-browser-storage-experimental-package) に関する記事を参照してください。

>[!div class="step-by-step"]
>[前へ](pages-routing-layouts.md)
>[次へ](forms-validation.md)
