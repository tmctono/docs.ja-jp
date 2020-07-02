---
ms.openlocfilehash: 6af8e97423c04abca25feb8d77ea9ab6e198a4f0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620330"
---
### <a name="objectcontexttranslate-and-objectcontextexecutestorequery-now-support-enum-type"></a><span data-ttu-id="3cbac-101">ObjectContext.Translate と ObjectContext.ExecuteStoreQuery で列挙型がサポートされるようになった</span><span class="sxs-lookup"><span data-stu-id="3cbac-101">ObjectContext.Translate and ObjectContext.ExecuteStoreQuery now support enum type</span></span>

#### <a name="details"></a><span data-ttu-id="3cbac-102">説明</span><span class="sxs-lookup"><span data-stu-id="3cbac-102">Details</span></span>

<span data-ttu-id="3cbac-103">.NET Framework 4.0 では、<code>ObjectContext.Translate</code> および <code>ObjectContext.ExecuteStoreQuery</code> メソッドのジェネリック パラメーター <code>T</code> を列挙型にすることはできませんでした。</span><span class="sxs-lookup"><span data-stu-id="3cbac-103">In .NET Framework 4.0, the generic parameter <code>T</code> of <code>ObjectContext.Translate</code> and <code>ObjectContext.ExecuteStoreQuery</code> methods could not be an enum.</span></span> <span data-ttu-id="3cbac-104">このシナリオがサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="3cbac-104">That scenario is now supported.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="3cbac-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="3cbac-105">Suggestion</span></span>

<span data-ttu-id="3cbac-106">.NET Framework 4.0 では、列挙型に対して Translate または ExecuteStoreQuery が呼び出された場合、"0" が返されました。</span><span class="sxs-lookup"><span data-stu-id="3cbac-106">If Translate or ExecuteStoreQuery was called on an enum type in .NET Framework 4.0, '0' was returned.</span></span> <span data-ttu-id="3cbac-107">この動作が望ましい場合は、呼び出しを定数 0 (または同等の列挙型) に置き換えてください。</span><span class="sxs-lookup"><span data-stu-id="3cbac-107">If that behavior was desirable, the calls should be replaced with a constant 0 (or the enum equivalent of it).</span></span>

| <span data-ttu-id="3cbac-108">名前</span><span class="sxs-lookup"><span data-stu-id="3cbac-108">Name</span></span>    | <span data-ttu-id="3cbac-109">[値]</span><span class="sxs-lookup"><span data-stu-id="3cbac-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="3cbac-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="3cbac-110">Scope</span></span>   |<span data-ttu-id="3cbac-111">エッジ</span><span class="sxs-lookup"><span data-stu-id="3cbac-111">Edge</span></span>|
|<span data-ttu-id="3cbac-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="3cbac-112">Version</span></span>|<span data-ttu-id="3cbac-113">4.5</span><span class="sxs-lookup"><span data-stu-id="3cbac-113">4.5</span></span>|
|<span data-ttu-id="3cbac-114">種類</span><span class="sxs-lookup"><span data-stu-id="3cbac-114">Type</span></span>|<span data-ttu-id="3cbac-115">ランタイム</span><span class="sxs-lookup"><span data-stu-id="3cbac-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="3cbac-116">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="3cbac-116">Affected APIs</span></span>

-<xref:System.Data.Objects.ObjectContext.Translate%60%601(System.Data.Common.DbDataReader)?displayProperty=nameWithType></li><li><xref:System.Data.Objects.ObjectContext.Translate%60%601(System.Data.Common.DbDataReader,System.String,System.Data.Objects.MergeOption)?displayProperty=nameWithType></li><li><xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601(System.String,System.Object[])?displayProperty=nameWithType></li><li><xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601(System.String,System.String,System.Data.Objects.MergeOption,System.Object[])?displayProperty=nameWithType></li></ul>|
