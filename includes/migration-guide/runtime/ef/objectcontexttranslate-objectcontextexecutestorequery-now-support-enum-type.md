---
ms.openlocfilehash: 1d2d6133683360b97569e49402e7c8c4d182b65d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804380"
---
### <a name="objectcontexttranslate-and-objectcontextexecutestorequery-now-support-enum-type"></a><span data-ttu-id="ff6ad-101">ObjectContext.Translate と ObjectContext.ExecuteStoreQuery で列挙型がサポートされるようになった</span><span class="sxs-lookup"><span data-stu-id="ff6ad-101">ObjectContext.Translate and ObjectContext.ExecuteStoreQuery now support enum type</span></span>

|   |   |
|---|---|
|<span data-ttu-id="ff6ad-102">説明</span><span class="sxs-lookup"><span data-stu-id="ff6ad-102">Details</span></span>|<span data-ttu-id="ff6ad-103">.NET Framework 4.0 では、<code>ObjectContext.Translate</code> および <code>ObjectContext.ExecuteStoreQuery</code> メソッドのジェネリック パラメーター <code>T</code> を列挙型にすることはできませんでした。</span><span class="sxs-lookup"><span data-stu-id="ff6ad-103">In .NET Framework 4.0, the generic parameter <code>T</code> of <code>ObjectContext.Translate</code> and <code>ObjectContext.ExecuteStoreQuery</code> methods could not be an enum.</span></span> <span data-ttu-id="ff6ad-104">このシナリオがサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="ff6ad-104">That scenario is now supported.</span></span>|
|<span data-ttu-id="ff6ad-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="ff6ad-105">Suggestion</span></span>|<span data-ttu-id="ff6ad-106">.NET Framework 4.0 では、列挙型に対して Translate または ExecuteStoreQuery が呼び出された場合、"0" が返されました。</span><span class="sxs-lookup"><span data-stu-id="ff6ad-106">If Translate or ExecuteStoreQuery was called on an enum type in .NET Framework 4.0, '0' was returned.</span></span> <span data-ttu-id="ff6ad-107">この動作が望ましい場合は、呼び出しを定数 0 (または同等の列挙型) に置き換えてください。</span><span class="sxs-lookup"><span data-stu-id="ff6ad-107">If that behavior was desirable, the calls should be replaced with a constant 0 (or the enum equivalent of it).</span></span>|
|<span data-ttu-id="ff6ad-108">スコープ</span><span class="sxs-lookup"><span data-stu-id="ff6ad-108">Scope</span></span>|<span data-ttu-id="ff6ad-109">エッジ</span><span class="sxs-lookup"><span data-stu-id="ff6ad-109">Edge</span></span>|
|<span data-ttu-id="ff6ad-110">Version</span><span class="sxs-lookup"><span data-stu-id="ff6ad-110">Version</span></span>|<span data-ttu-id="ff6ad-111">4.5</span><span class="sxs-lookup"><span data-stu-id="ff6ad-111">4.5</span></span>|
|<span data-ttu-id="ff6ad-112">型</span><span class="sxs-lookup"><span data-stu-id="ff6ad-112">Type</span></span>|<span data-ttu-id="ff6ad-113">ランタイム</span><span class="sxs-lookup"><span data-stu-id="ff6ad-113">Runtime</span></span>|
|<span data-ttu-id="ff6ad-114">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="ff6ad-114">Affected APIs</span></span>|<ul><li><xref:System.Data.Objects.ObjectContext.Translate%60%601(System.Data.Common.DbDataReader)?displayProperty=nameWithType></li><li><xref:System.Data.Objects.ObjectContext.Translate%60%601(System.Data.Common.DbDataReader,System.String,System.Data.Objects.MergeOption)?displayProperty=nameWithType></li><li><xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601(System.String,System.Object[])?displayProperty=nameWithType></li><li><xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601(System.String,System.String,System.Data.Objects.MergeOption,System.Object[])?displayProperty=nameWithType></li></ul>|
