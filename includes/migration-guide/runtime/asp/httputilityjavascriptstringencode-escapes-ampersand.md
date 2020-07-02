---
ms.openlocfilehash: d587e542a72d584502ac3ac892619cc38b88ef77
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620144"
---
### <a name="httputilityjavascriptstringencode-escapes-ampersand"></a><span data-ttu-id="05191-101">HttpUtility.JavaScriptStringEncode でアンパサンドがエスケープされる</span><span class="sxs-lookup"><span data-stu-id="05191-101">HttpUtility.JavaScriptStringEncode escapes ampersand</span></span>

#### <a name="details"></a><span data-ttu-id="05191-102">説明</span><span class="sxs-lookup"><span data-stu-id="05191-102">Details</span></span>

<span data-ttu-id="05191-103">.NET Framework 4.5 以降では、<xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=fullName> でアンパサンド (&amp;) 文字がエスケープされます。</span><span class="sxs-lookup"><span data-stu-id="05191-103">Starting with the .NET Framework 4.5, <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=fullName> escapes the ampersand (&amp;) character.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="05191-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="05191-104">Suggestion</span></span>

<span data-ttu-id="05191-105">アプリがこのメソッドの以前の動作に依存している場合、構成ファイルの [ASP.NET appSettings 要素](https://docs.microsoft.com/previous-versions/aspnet/hh975440(v=vs.120)) に aspnet:JavaScriptDoNotEncodeAmpersand 設定を追加できます。</span><span class="sxs-lookup"><span data-stu-id="05191-105">If your app depends on the previous behavior of this method, you can add an aspnet:JavaScriptDoNotEncodeAmpersand setting to the [ASP.NET appSettings element](https://docs.microsoft.com/previous-versions/aspnet/hh975440(v=vs.120)) in your configuration file.</span></span>

| <span data-ttu-id="05191-106">名前</span><span class="sxs-lookup"><span data-stu-id="05191-106">Name</span></span>    | <span data-ttu-id="05191-107">[値]</span><span class="sxs-lookup"><span data-stu-id="05191-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="05191-108">スコープ</span><span class="sxs-lookup"><span data-stu-id="05191-108">Scope</span></span>   |<span data-ttu-id="05191-109">マイナー</span><span class="sxs-lookup"><span data-stu-id="05191-109">Minor</span></span>|
|<span data-ttu-id="05191-110">バージョン</span><span class="sxs-lookup"><span data-stu-id="05191-110">Version</span></span>|<span data-ttu-id="05191-111">4.5</span><span class="sxs-lookup"><span data-stu-id="05191-111">4.5</span></span>|
|<span data-ttu-id="05191-112">種類</span><span class="sxs-lookup"><span data-stu-id="05191-112">Type</span></span>|<span data-ttu-id="05191-113">ランタイム</span><span class="sxs-lookup"><span data-stu-id="05191-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="05191-114">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="05191-114">Affected APIs</span></span>

-<xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=nameWithType></li><li><xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String,System.Boolean)?displayProperty=nameWithType></li></ul>|
