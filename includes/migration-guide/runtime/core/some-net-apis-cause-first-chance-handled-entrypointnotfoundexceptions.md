---
ms.openlocfilehash: ed526095459a48aa37b585dfed79cc12b9fb9e56
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622046"
---
### <a name="some-net-apis-cause-first-chance-handled-entrypointnotfoundexceptions"></a><span data-ttu-id="2738d-101">一部の .NET API がファースト チャンス (処理済み) EntryPointNotFoundExceptions の原因になります</span><span class="sxs-lookup"><span data-stu-id="2738d-101">Some .NET APIs cause first chance (handled) EntryPointNotFoundExceptions</span></span>

#### <a name="details"></a><span data-ttu-id="2738d-102">説明</span><span class="sxs-lookup"><span data-stu-id="2738d-102">Details</span></span>

<span data-ttu-id="2738d-103">.NET Framework 4.5 では、少数の .NET メソッドが、ファースト チャンス <xref:System.EntryPointNotFoundException?displayProperty=fullName> をスローするようになりました。</span><span class="sxs-lookup"><span data-stu-id="2738d-103">In the .NET Framework 4.5, a small number of .NET methods began throwing first chance <xref:System.EntryPointNotFoundException?displayProperty=fullName>s.</span></span> <span data-ttu-id="2738d-104">これらの例外は .NET Framework 内で処理されますが、ファースト チャンス例外を予期していないテスト自動化を中断することがありました。</span><span class="sxs-lookup"><span data-stu-id="2738d-104">These exceptions were handled within the .NET Framework, but could break test automation that did not expect the first chance exceptions.</span></span> <span data-ttu-id="2738d-105">これらと同じ API は、HighVersionLie が有効なとき、一部の ApiVerifier シナリオを中断させます。</span><span class="sxs-lookup"><span data-stu-id="2738d-105">These same APIs break some ApiVerifier scenarios when HighVersionLie is enabled.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="2738d-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="2738d-106">Suggestion</span></span>

<span data-ttu-id="2738d-107">このバグは、.NET Framework 4.5.1 にアップグレードすることによって回避できます。</span><span class="sxs-lookup"><span data-stu-id="2738d-107">This bug can be avoided by upgrading to .NET Framework 4.5.1.</span></span> <span data-ttu-id="2738d-108">または、ファースト チャンス <xref:System.EntryPointNotFoundException?displayProperty=fullName> で中断しないように、テスト自動化を更新できます。</span><span class="sxs-lookup"><span data-stu-id="2738d-108">Alternatively, test automation can be updated to not break on first-chance <xref:System.EntryPointNotFoundException?displayProperty=fullName>s.</span></span>

| <span data-ttu-id="2738d-109">名前</span><span class="sxs-lookup"><span data-stu-id="2738d-109">Name</span></span>    | <span data-ttu-id="2738d-110">[値]</span><span class="sxs-lookup"><span data-stu-id="2738d-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="2738d-111">スコープ</span><span class="sxs-lookup"><span data-stu-id="2738d-111">Scope</span></span>   |<span data-ttu-id="2738d-112">エッジ</span><span class="sxs-lookup"><span data-stu-id="2738d-112">Edge</span></span>|
|<span data-ttu-id="2738d-113">バージョン</span><span class="sxs-lookup"><span data-stu-id="2738d-113">Version</span></span>|<span data-ttu-id="2738d-114">4.5</span><span class="sxs-lookup"><span data-stu-id="2738d-114">4.5</span></span>|
|<span data-ttu-id="2738d-115">種類</span><span class="sxs-lookup"><span data-stu-id="2738d-115">Type</span></span>|<span data-ttu-id="2738d-116">ランタイム</span><span class="sxs-lookup"><span data-stu-id="2738d-116">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="2738d-117">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="2738d-117">Affected APIs</span></span>

-<xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String,System.String)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String,System.String,System.Object[])?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.%23ctor(System.Type)></li></ul>|
