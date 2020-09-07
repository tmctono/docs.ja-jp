---
ms.openlocfilehash: 17fde81f9734966692c9f41d2213f8682dedea46
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496913"
---
### <a name="contractinvariant-or-contractrequirestexception-do-not-consider-stringisnullorempty-to-be-pure"></a><span data-ttu-id="47208-101">Contract.Invariant または Contract.Requires\<TException> が String.IsNullOrEmpty の純粋性を考慮しない</span><span class="sxs-lookup"><span data-stu-id="47208-101">Contract.Invariant or Contract.Requires\<TException> do not consider String.IsNullOrEmpty to be pure</span></span>

#### <a name="details"></a><span data-ttu-id="47208-102">説明</span><span class="sxs-lookup"><span data-stu-id="47208-102">Details</span></span>

<span data-ttu-id="47208-103">.NET Framework 4.6.1 が対象のアプリでは、<xref:System.Diagnostics.Contracts.Contract.Invariant%2A?displayProperty=nameWithType> の不変コントラクトまたは <xref:System.Diagnostics.Contracts.Contract.Requires%2A?displayProperty=nameWithType)> の実行前の状態のコントラクトが <xref:System.String.IsNullOrEmpty%2A?displayProperty=nameWithType> メソッドを呼び出した場合、リライターはコンパイラの警告 CC1036:&quot;Detected call to method 'System.String.IsNullOrWhiteSpace(System.String)' without [Pure] in method.&quot; を生成します。これはコンパイラ エラーではなく、コンパイラ警告です。</span><span class="sxs-lookup"><span data-stu-id="47208-103">For apps that target the .NET Framework 4.6.1, if the invariant contract for <xref:System.Diagnostics.Contracts.Contract.Invariant%2A?displayProperty=nameWithType> or the precondition contract for <xref:System.Diagnostics.Contracts.Contract.Requires%2A?displayProperty=nameWithType)> calls the <xref:System.String.IsNullOrEmpty%2A?displayProperty=nameWithType> method, the rewriter emits compiler warning CC1036: &quot;Detected call to method 'System.String.IsNullOrWhteSpace(System.String)' without [Pure] in method.&quot; This is a compiler warning rather than a compiler error.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="47208-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="47208-104">Suggestion</span></span>

<span data-ttu-id="47208-105">この動作については [GitHubの問題 #339](https://github.com/Microsoft/CodeContracts/issues/339) で報告されています。</span><span class="sxs-lookup"><span data-stu-id="47208-105">This behavior was addressed in [GitHub Issue #339](https://github.com/Microsoft/CodeContracts/issues/339).</span></span> <span data-ttu-id="47208-106">この警告が表示されないようにするには、コード コントラクト ツールのソース コードの更新バージョンを [GitHub](https://github.com/Microsoft/CodeContracts/blob/master/README.md) からダウンロードしてコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="47208-106">To eliminate this warning, you can download and compile an updated version of the source code for the Code Contracts tool from [GitHub](https://github.com/Microsoft/CodeContracts/blob/master/README.md).</span></span> <span data-ttu-id="47208-107">ページ下部から情報をダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="47208-107">Download information is found at the bottom of the page.</span></span>

| <span data-ttu-id="47208-108">名前</span><span class="sxs-lookup"><span data-stu-id="47208-108">Name</span></span>    | <span data-ttu-id="47208-109">[値]</span><span class="sxs-lookup"><span data-stu-id="47208-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="47208-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="47208-110">Scope</span></span>   |<span data-ttu-id="47208-111">マイナー</span><span class="sxs-lookup"><span data-stu-id="47208-111">Minor</span></span>|
|<span data-ttu-id="47208-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="47208-112">Version</span></span>|<span data-ttu-id="47208-113">4.6.1</span><span class="sxs-lookup"><span data-stu-id="47208-113">4.6.1</span></span>|
|<span data-ttu-id="47208-114">種類</span><span class="sxs-lookup"><span data-stu-id="47208-114">Type</span></span>|<span data-ttu-id="47208-115">ランタイム</span><span class="sxs-lookup"><span data-stu-id="47208-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="47208-116">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="47208-116">Affected APIs</span></span>

- <xref:System.Diagnostics.Contracts.Contract.Invariant(System.Boolean)?displayProperty=nameWithType>
- <xref:System.Diagnostics.Contracts.Contract.Requires(System.Boolean)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Diagnostics.Contracts.Contract.Invariant(System.Boolean)`
- `M:System.Diagnostics.Contracts.Contract.Requires(System.Boolean)`

-->
