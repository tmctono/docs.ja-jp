---
ms.openlocfilehash: 06424c4fa40343a881356c20003300f65e93efbb
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496398"
---
### <a name="wf-serializes-expressionsliterallttgt-datetimes-differently-now-breaks-custom-xaml-parsers"></a><span data-ttu-id="441fd-101">WF による Expressions.Literal&lt;T&gt; DateTimes のシリアル化の方法が変わった (カスタム XAML パーサーが機能しなくなる)</span><span class="sxs-lookup"><span data-stu-id="441fd-101">WF serializes Expressions.Literal&lt;T&gt; DateTimes differently now (breaks custom XAML parsers)</span></span>

#### <a name="details"></a><span data-ttu-id="441fd-102">説明</span><span class="sxs-lookup"><span data-stu-id="441fd-102">Details</span></span>

<span data-ttu-id="441fd-103">関連する <xref:System.Windows.Markup.ValueSerializer> オブジェクトは、Second コンポーネントと <xref:System.DateTime.Millisecond?displayProperty=fullName> コンポーネントが非ゼロで (<xref:System.DateTime?displayProperty=fullName> 値の場合)、<xref:System.DateTime.Kind> プロパティが Unspecified ではない <xref:System.DateTime?displayProperty=fullName> オブジェクトまたは <xref:System.DateTimeOffset?displayProperty=fullName> オブジェクトを文字列ではなくプロパティ要素構文に変換します。</span><span class="sxs-lookup"><span data-stu-id="441fd-103">The associated <xref:System.Windows.Markup.ValueSerializer> object will convert a <xref:System.DateTime?displayProperty=fullName> or <xref:System.DateTimeOffset?displayProperty=fullName> object whose Second and <xref:System.DateTime.Millisecond?displayProperty=fullName> components are non-zero and (for a <xref:System.DateTime?displayProperty=fullName> value) whose <xref:System.DateTime.Kind> property is not Unspecified to property element syntax instead of a string.</span></span> <span data-ttu-id="441fd-104">この変更により、<xref:System.DateTime?displayProperty=fullName> 値と <xref:System.DateTimeOffset?displayProperty=fullName> 値を往復させることができるようになります。</span><span class="sxs-lookup"><span data-stu-id="441fd-104">This change allows <xref:System.DateTime?displayProperty=fullName> and <xref:System.DateTimeOffset?displayProperty=fullName> values to be round-tripped.</span></span> <span data-ttu-id="441fd-105">入力 XAML が属性構文であると想定するカスタム XAML パーサーは正しく機能しません。</span><span class="sxs-lookup"><span data-stu-id="441fd-105">Custom XAML parsers that assume that input XAML is in the attribute syntax will not function correctly.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="441fd-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="441fd-106">Suggestion</span></span>

<span data-ttu-id="441fd-107">この変更により、<xref:System.DateTime?displayProperty=fullName> 値と <xref:System.DateTimeOffset?displayProperty=fullName> 値を往復させることができるようになります。</span><span class="sxs-lookup"><span data-stu-id="441fd-107">This change allows <xref:System.DateTime?displayProperty=fullName> and <xref:System.DateTimeOffset?displayProperty=fullName> values to be round-tripped.</span></span> <span data-ttu-id="441fd-108">入力 XAML が属性構文であると想定するカスタム XAML パーサーは正しく機能しません。</span><span class="sxs-lookup"><span data-stu-id="441fd-108">Custom XAML parsers that assume that input XAML is in the attribute syntax will not function correctly.</span></span>

| <span data-ttu-id="441fd-109">名前</span><span class="sxs-lookup"><span data-stu-id="441fd-109">Name</span></span>    | <span data-ttu-id="441fd-110">[値]</span><span class="sxs-lookup"><span data-stu-id="441fd-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="441fd-111">スコープ</span><span class="sxs-lookup"><span data-stu-id="441fd-111">Scope</span></span>   |<span data-ttu-id="441fd-112">エッジ</span><span class="sxs-lookup"><span data-stu-id="441fd-112">Edge</span></span>|
|<span data-ttu-id="441fd-113">バージョン</span><span class="sxs-lookup"><span data-stu-id="441fd-113">Version</span></span>|<span data-ttu-id="441fd-114">4.5</span><span class="sxs-lookup"><span data-stu-id="441fd-114">4.5</span></span>|
|<span data-ttu-id="441fd-115">種類</span><span class="sxs-lookup"><span data-stu-id="441fd-115">Type</span></span>|<span data-ttu-id="441fd-116">ランタイム</span><span class="sxs-lookup"><span data-stu-id="441fd-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="441fd-117">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="441fd-117">Affected APIs</span></span>

<span data-ttu-id="441fd-118">API 分析では検出できません。</span><span class="sxs-lookup"><span data-stu-id="441fd-118">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
