---
ms.openlocfilehash: 87013a04f7ff975e40a3c49c41c1c5acc2374066
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620410"
---
### <a name="wf-serializes-expressionsliterallttgt-datetimes-differently-now-breaks-custom-xaml-parsers"></a><span data-ttu-id="e0bbf-101">WF による Expressions.Literal&lt;T&gt; DateTimes のシリアル化の方法が変わった (カスタム XAML パーサーが機能しなくなる)</span><span class="sxs-lookup"><span data-stu-id="e0bbf-101">WF serializes Expressions.Literal&lt;T&gt; DateTimes differently now (breaks custom XAML parsers)</span></span>

#### <a name="details"></a><span data-ttu-id="e0bbf-102">説明</span><span class="sxs-lookup"><span data-stu-id="e0bbf-102">Details</span></span>

<span data-ttu-id="e0bbf-103">関連する <xref:System.Windows.Markup.ValueSerializer> オブジェクトは、Second コンポーネントと <xref:System.DateTime.Millisecond?displayProperty=fullName> コンポーネントが非ゼロで (<xref:System.DateTime?displayProperty=fullName> 値の場合)、<xref:System.DateTime.Kind> プロパティが Unspecified ではない <xref:System.DateTime?displayProperty=fullName> オブジェクトまたは <xref:System.DateTimeOffset?displayProperty=fullName> オブジェクトを文字列ではなくプロパティ要素構文に変換します。</span><span class="sxs-lookup"><span data-stu-id="e0bbf-103">The associated <xref:System.Windows.Markup.ValueSerializer> object will convert a <xref:System.DateTime?displayProperty=fullName> or <xref:System.DateTimeOffset?displayProperty=fullName> object whose Second and <xref:System.DateTime.Millisecond?displayProperty=fullName> components are non-zero and (for a <xref:System.DateTime?displayProperty=fullName> value) whose <xref:System.DateTime.Kind> property is not Unspecified to property element syntax instead of a string.</span></span> <span data-ttu-id="e0bbf-104">この変更により、<xref:System.DateTime?displayProperty=fullName> 値と <xref:System.DateTimeOffset?displayProperty=fullName> 値を往復させることができるようになります。</span><span class="sxs-lookup"><span data-stu-id="e0bbf-104">This change allows <xref:System.DateTime?displayProperty=fullName> and <xref:System.DateTimeOffset?displayProperty=fullName> values to be round-tripped.</span></span> <span data-ttu-id="e0bbf-105">入力 XAML が属性構文であると想定するカスタム XAML パーサーは正しく機能しません。</span><span class="sxs-lookup"><span data-stu-id="e0bbf-105">Custom XAML parsers that assume that input XAML is in the attribute syntax will not function correctly.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="e0bbf-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="e0bbf-106">Suggestion</span></span>

<span data-ttu-id="e0bbf-107">この変更により、<xref:System.DateTime?displayProperty=fullName> 値と <xref:System.DateTimeOffset?displayProperty=fullName> 値を往復させることができるようになります。</span><span class="sxs-lookup"><span data-stu-id="e0bbf-107">This change allows <xref:System.DateTime?displayProperty=fullName> and <xref:System.DateTimeOffset?displayProperty=fullName> values to be round-tripped.</span></span> <span data-ttu-id="e0bbf-108">入力 XAML が属性構文であると想定するカスタム XAML パーサーは正しく機能しません。</span><span class="sxs-lookup"><span data-stu-id="e0bbf-108">Custom XAML parsers that assume that input XAML is in the attribute syntax will not function correctly.</span></span>

| <span data-ttu-id="e0bbf-109">名前</span><span class="sxs-lookup"><span data-stu-id="e0bbf-109">Name</span></span>    | <span data-ttu-id="e0bbf-110">[値]</span><span class="sxs-lookup"><span data-stu-id="e0bbf-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="e0bbf-111">スコープ</span><span class="sxs-lookup"><span data-stu-id="e0bbf-111">Scope</span></span>   |<span data-ttu-id="e0bbf-112">エッジ</span><span class="sxs-lookup"><span data-stu-id="e0bbf-112">Edge</span></span>|
|<span data-ttu-id="e0bbf-113">バージョン</span><span class="sxs-lookup"><span data-stu-id="e0bbf-113">Version</span></span>|<span data-ttu-id="e0bbf-114">4.5</span><span class="sxs-lookup"><span data-stu-id="e0bbf-114">4.5</span></span>|
|<span data-ttu-id="e0bbf-115">種類</span><span class="sxs-lookup"><span data-stu-id="e0bbf-115">Type</span></span>|<span data-ttu-id="e0bbf-116">ランタイム</span><span class="sxs-lookup"><span data-stu-id="e0bbf-116">Runtime</span></span>|
