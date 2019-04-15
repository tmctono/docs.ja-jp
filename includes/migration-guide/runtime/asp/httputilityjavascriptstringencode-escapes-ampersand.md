---
ms.openlocfilehash: 0056baa1e5f0cdc5bfcf8b0e83c9490ec5722926
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235706"
---
### <a name="httputilityjavascriptstringencode-escapes-ampersand"></a><span data-ttu-id="5ecf2-101">HttpUtility.JavaScriptStringEncode でアンパサンドがエスケープされる</span><span class="sxs-lookup"><span data-stu-id="5ecf2-101">HttpUtility.JavaScriptStringEncode escapes ampersand</span></span>

|   |   |
|---|---|
|<span data-ttu-id="5ecf2-102">説明</span><span class="sxs-lookup"><span data-stu-id="5ecf2-102">Details</span></span>|<span data-ttu-id="5ecf2-103">.NET Framework 4.5 以降では、<xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=name> でアンパサンド (&amp;) 文字がエスケープされます。</span><span class="sxs-lookup"><span data-stu-id="5ecf2-103">Starting with the .NET Framework 4.5, <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=name> escapes the ampersand (&amp;) character.</span></span>|
|<span data-ttu-id="5ecf2-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="5ecf2-104">Suggestion</span></span>|<span data-ttu-id="5ecf2-105">アプリがこのメソッドの以前の動作に依存している場合、構成ファイルの [ASP.NET appSettings 要素](https://docs.microsoft.com/previous-versions/aspnet/hh975440(v=vs.120)) に aspnet:JavaScriptDoNotEncodeAmpersand 設定を追加できます。</span><span class="sxs-lookup"><span data-stu-id="5ecf2-105">If your app depends on the previous behavior of this method, you can add an aspnet:JavaScriptDoNotEncodeAmpersand setting to the [ASP.NET appSettings element](https://docs.microsoft.com/previous-versions/aspnet/hh975440(v=vs.120)) in your configuration file.</span></span>|
|<span data-ttu-id="5ecf2-106">スコープ</span><span class="sxs-lookup"><span data-stu-id="5ecf2-106">Scope</span></span>|<span data-ttu-id="5ecf2-107">マイナー</span><span class="sxs-lookup"><span data-stu-id="5ecf2-107">Minor</span></span>|
|<span data-ttu-id="5ecf2-108">Version</span><span class="sxs-lookup"><span data-stu-id="5ecf2-108">Version</span></span>|<span data-ttu-id="5ecf2-109">4.5</span><span class="sxs-lookup"><span data-stu-id="5ecf2-109">4.5</span></span>|
|<span data-ttu-id="5ecf2-110">型</span><span class="sxs-lookup"><span data-stu-id="5ecf2-110">Type</span></span>|<span data-ttu-id="5ecf2-111">ランタイム</span><span class="sxs-lookup"><span data-stu-id="5ecf2-111">Runtime</span></span>|
|<span data-ttu-id="5ecf2-112">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="5ecf2-112">Affected APIs</span></span>|<ul><li><xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=nameWithType></li><li><xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String,System.Boolean)?displayProperty=nameWithType></li></ul>|
