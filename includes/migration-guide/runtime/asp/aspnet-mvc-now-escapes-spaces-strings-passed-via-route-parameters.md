---
ms.openlocfilehash: afbf34710c75d0f0586ddfdb2e7937d8d76d5399
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497168"
---
### <a name="aspnet-mvc-now-escapes-spaces-in-strings-passed-in-via-route-parameters"></a><span data-ttu-id="395ba-101">ASP.NET MVC は、ルート パラメーターで渡された文字列内のスペースをエスケープするようになりました</span><span class="sxs-lookup"><span data-stu-id="395ba-101">ASP.NET MVC now escapes spaces in strings passed in via route parameters</span></span>

#### <a name="details"></a><span data-ttu-id="395ba-102">説明</span><span class="sxs-lookup"><span data-stu-id="395ba-102">Details</span></span>

<span data-ttu-id="395ba-103">RFC 2396 に準拠するために、ルートからアクション パラメーターを設定するときに、ルートのパスに含まれるスペースがエスケープされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="395ba-103">In order to conform to RFC 2396, spaces in route paths are now escaped when populating action parameters from a route.</span></span> <span data-ttu-id="395ba-104">そのため、<code>/controller/action/some data</code> は以前はルート <code>/controller/action/{data}</code> し、<code>some data</code> をデータ パラメーターとして与えましたが、代わりに <code>some%20data</code> を与えるようになります。</span><span class="sxs-lookup"><span data-stu-id="395ba-104">So, whereas  <code>/controller/action/some data</code> would previously match the route <code>/controller/action/{data}</code> and provide <code>some data</code> as the data parameter, it will now provide <code>some%20data</code> instead.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="395ba-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="395ba-105">Suggestion</span></span>

<span data-ttu-id="395ba-106">ルートからの文字列パラメーターをエスケープ解除するように、コードを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="395ba-106">Code should be updated to unescape string parameters from a route.</span></span> <span data-ttu-id="395ba-107">元の URI が必要な場合は、<xref:System.Net.HttpWebRequest.RequestUri>.OriginalString API でアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="395ba-107">If the original URI is needed, it can be accessed with the <xref:System.Net.HttpWebRequest.RequestUri>.OriginalString API.</span></span>

| <span data-ttu-id="395ba-108">名前</span><span class="sxs-lookup"><span data-stu-id="395ba-108">Name</span></span>    | <span data-ttu-id="395ba-109">[値]</span><span class="sxs-lookup"><span data-stu-id="395ba-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="395ba-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="395ba-110">Scope</span></span>   |<span data-ttu-id="395ba-111">マイナー</span><span class="sxs-lookup"><span data-stu-id="395ba-111">Minor</span></span>|
|<span data-ttu-id="395ba-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="395ba-112">Version</span></span>|<span data-ttu-id="395ba-113">4.5.2</span><span class="sxs-lookup"><span data-stu-id="395ba-113">4.5.2</span></span>|
|<span data-ttu-id="395ba-114">種類</span><span class="sxs-lookup"><span data-stu-id="395ba-114">Type</span></span>|<span data-ttu-id="395ba-115">ランタイム</span><span class="sxs-lookup"><span data-stu-id="395ba-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="395ba-116">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="395ba-116">Affected APIs</span></span>

- <xref:System.Web.Mvc.RouteAttribute.%23ctor(System.String)>

<!--

#### Affected APIs

- `M:System.Web.Mvc.RouteAttribute.#ctor(System.String)`

-->
