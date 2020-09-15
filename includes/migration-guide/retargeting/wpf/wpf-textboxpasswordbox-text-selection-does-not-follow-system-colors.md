---
ms.openlocfilehash: 7c2e80669d9ef27f87cde9442d8eeab0ee31a524
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614976"
---
### <a name="wpf-textboxpasswordbox-text-selection-does-not-follow-system-colors"></a><span data-ttu-id="d6e4b-101">WPF TextBox/PasswordBox のテキスト選択がシステム カラーに従っていない</span><span class="sxs-lookup"><span data-stu-id="d6e4b-101">WPF TextBox/PasswordBox Text Selection Does Not Follow System Colors</span></span>

#### <a name="details"></a><span data-ttu-id="d6e4b-102">説明</span><span class="sxs-lookup"><span data-stu-id="d6e4b-102">Details</span></span>

<span data-ttu-id="d6e4b-103">.NET Framework 4.7.1 以前のバージョンでは、WPF の `System.Windows.Controls.TextBox` および `System.Windows.Controls.PasswordBox` は装飾層のテキスト選択のみをレンダリングできました。</span><span class="sxs-lookup"><span data-stu-id="d6e4b-103">In .NET Framework 4.7.1 and earlier versions, WPF `System.Windows.Controls.TextBox` and `System.Windows.Controls.PasswordBox` could only render a text selection in the Adorner layer.</span></span> <span data-ttu-id="d6e4b-104">そのため、一部のシステム テーマではテキストが遮られ、読みにくくなっていました。</span><span class="sxs-lookup"><span data-stu-id="d6e4b-104">In some system themes this would occlude text, making it hard to read.</span></span>  <span data-ttu-id="d6e4b-105">.NET framework 4.7.2 以降では、開発者は、この問題を軽減する非装飾ベースの選択レンダリング スキームを有効にするオプションを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="d6e4b-105">In .NET Framework 4.7.2 and later, developers have an option of enabling a non-Adorner-based selection rendering scheme that alleviates this issue.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d6e4b-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="d6e4b-106">Suggestion</span></span>

<span data-ttu-id="d6e4b-107">この変更を利用する開発者は、次の AppContext フラグを適切に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6e4b-107">A developer who wants to utilize this change must set the following AppContext flag appropriately.</span></span>  <span data-ttu-id="d6e4b-108">この機能を利用するには、インストールされている .NET Framework のバージョンが 4.7.2 以上である必要があります。非装飾ベースの選択を有効にするには、次の AppContext フラグを使用します。</span><span class="sxs-lookup"><span data-stu-id="d6e4b-108">To utilize this feature, the installed .NET Framework version must be 4.7.2 or greater.To enabled the non-adorner-based selection, use the following AppContext flag.</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.Text.UseAdornerForTextboxSelectionRendering=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="d6e4b-109">名前</span><span class="sxs-lookup"><span data-stu-id="d6e4b-109">Name</span></span>    | <span data-ttu-id="d6e4b-110">[値]</span><span class="sxs-lookup"><span data-stu-id="d6e4b-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d6e4b-111">スコープ</span><span class="sxs-lookup"><span data-stu-id="d6e4b-111">Scope</span></span>   | <span data-ttu-id="d6e4b-112">エッジ</span><span class="sxs-lookup"><span data-stu-id="d6e4b-112">Edge</span></span>        |
| <span data-ttu-id="d6e4b-113">バージョン</span><span class="sxs-lookup"><span data-stu-id="d6e4b-113">Version</span></span> | <span data-ttu-id="d6e4b-114">4.7.2</span><span class="sxs-lookup"><span data-stu-id="d6e4b-114">4.7.2</span></span>       |
| <span data-ttu-id="d6e4b-115">種類</span><span class="sxs-lookup"><span data-stu-id="d6e4b-115">Type</span></span>    | <span data-ttu-id="d6e4b-116">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="d6e4b-116">Retargeting</span></span> |
