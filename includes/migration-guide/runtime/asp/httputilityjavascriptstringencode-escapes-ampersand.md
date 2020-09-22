---
ms.openlocfilehash: b648aee35ff44730f545f0fa06f4e0a86615dece
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606340"
---
### <a name="httputilityjavascriptstringencode-escapes-ampersand"></a><span data-ttu-id="7bb81-101">HttpUtility.JavaScriptStringEncode でアンパサンドがエスケープされる</span><span class="sxs-lookup"><span data-stu-id="7bb81-101">HttpUtility.JavaScriptStringEncode escapes ampersand</span></span>

#### <a name="details"></a><span data-ttu-id="7bb81-102">説明</span><span class="sxs-lookup"><span data-stu-id="7bb81-102">Details</span></span>

<span data-ttu-id="7bb81-103">.NET Framework 4.5 以降では、<xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=fullName> でアンパサンド (&amp;) 文字がエスケープされます。</span><span class="sxs-lookup"><span data-stu-id="7bb81-103">Starting with the .NET Framework 4.5, <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=fullName> escapes the ampersand (&amp;) character.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="7bb81-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="7bb81-104">Suggestion</span></span>

<span data-ttu-id="7bb81-105">アプリがこのメソッドの以前の動作に依存している場合、構成ファイルの [ASP.NET appSettings 要素](/previous-versions/aspnet/hh975440(v=vs.120)) に aspnet:JavaScriptDoNotEncodeAmpersand 設定を追加できます。</span><span class="sxs-lookup"><span data-stu-id="7bb81-105">If your app depends on the previous behavior of this method, you can add an aspnet:JavaScriptDoNotEncodeAmpersand setting to the [ASP.NET appSettings element](/previous-versions/aspnet/hh975440(v=vs.120)) in your configuration file.</span></span>

| <span data-ttu-id="7bb81-106">名前</span><span class="sxs-lookup"><span data-stu-id="7bb81-106">Name</span></span>    | <span data-ttu-id="7bb81-107">[値]</span><span class="sxs-lookup"><span data-stu-id="7bb81-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="7bb81-108">スコープ</span><span class="sxs-lookup"><span data-stu-id="7bb81-108">Scope</span></span>   |<span data-ttu-id="7bb81-109">マイナー</span><span class="sxs-lookup"><span data-stu-id="7bb81-109">Minor</span></span>|
|<span data-ttu-id="7bb81-110">バージョン</span><span class="sxs-lookup"><span data-stu-id="7bb81-110">Version</span></span>|<span data-ttu-id="7bb81-111">4.5</span><span class="sxs-lookup"><span data-stu-id="7bb81-111">4.5</span></span>|
|<span data-ttu-id="7bb81-112">種類</span><span class="sxs-lookup"><span data-stu-id="7bb81-112">Type</span></span>|<span data-ttu-id="7bb81-113">ランタイム</span><span class="sxs-lookup"><span data-stu-id="7bb81-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="7bb81-114">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="7bb81-114">Affected APIs</span></span>

- <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=nameWithType>
- <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String,System.Boolean)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Web.HttpUtility.JavaScriptStringEncode(System.String)`
- `M:System.Web.HttpUtility.JavaScriptStringEncode(System.String,System.Boolean)`

-->
