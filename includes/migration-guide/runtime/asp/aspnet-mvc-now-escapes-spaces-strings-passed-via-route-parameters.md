---
ms.openlocfilehash: 2278d82d5362fe217ca4bce02a052d4b440843c2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774264"
---
### <a name="aspnet-mvc-now-escapes-spaces-in-strings-passed-in-via-route-parameters"></a><span data-ttu-id="b59f2-101">ASP.NET MVC は、ルート パラメーターで渡された文字列内のスペースをエスケープするようになりました</span><span class="sxs-lookup"><span data-stu-id="b59f2-101">ASP.NET MVC now escapes spaces in strings passed in via route parameters</span></span>

|   |   |
|---|---|
|<span data-ttu-id="b59f2-102">説明</span><span class="sxs-lookup"><span data-stu-id="b59f2-102">Details</span></span>|<span data-ttu-id="b59f2-103">RFC 2396 に準拠するために、ルートからアクション パラメーターを設定するときに、ルートのパスに含まれるスペースがエスケープされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="b59f2-103">In order to conform to RFC 2396, spaces in route paths are now escaped when populating action parameters from a route.</span></span> <span data-ttu-id="b59f2-104">そのため、<code>/controller/action/some data</code> は以前はルート <code>/controller/action/{data}</code> し、<code>some data</code> をデータ パラメーターとして与えましたが、代わりに <code>some%20data</code> を与えるようになります。</span><span class="sxs-lookup"><span data-stu-id="b59f2-104">So, whereas  <code>/controller/action/some data</code> would previously match the route <code>/controller/action/{data}</code> and provide <code>some data</code> as the data parameter, it will now provide <code>some%20data</code> instead.</span></span>|
|<span data-ttu-id="b59f2-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="b59f2-105">Suggestion</span></span>|<span data-ttu-id="b59f2-106">ルートからの文字列パラメーターをエスケープ解除するように、コードを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b59f2-106">Code should be updated to unescape string parameters from a route.</span></span> <span data-ttu-id="b59f2-107">元の URI が必要な場合は、<xref:System.Net.HttpWebRequest.RequestUri>.OriginalString API でアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b59f2-107">If the original URI is needed, it can be accessed with the <xref:System.Net.HttpWebRequest.RequestUri>.OriginalString API.</span></span>|
|<span data-ttu-id="b59f2-108">スコープ</span><span class="sxs-lookup"><span data-stu-id="b59f2-108">Scope</span></span>|<span data-ttu-id="b59f2-109">マイナー</span><span class="sxs-lookup"><span data-stu-id="b59f2-109">Minor</span></span>|
|<span data-ttu-id="b59f2-110">Version</span><span class="sxs-lookup"><span data-stu-id="b59f2-110">Version</span></span>|<span data-ttu-id="b59f2-111">4.5.2</span><span class="sxs-lookup"><span data-stu-id="b59f2-111">4.5.2</span></span>|
|<span data-ttu-id="b59f2-112">型</span><span class="sxs-lookup"><span data-stu-id="b59f2-112">Type</span></span>|<span data-ttu-id="b59f2-113">ランタイム</span><span class="sxs-lookup"><span data-stu-id="b59f2-113">Runtime</span></span>|
|<span data-ttu-id="b59f2-114">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="b59f2-114">Affected APIs</span></span>|<ul><li><xref:System.Web.Mvc.RouteAttribute.%23ctor(System.String)?displayProperty=nameWithType></li></ul>|
