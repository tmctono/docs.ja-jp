---
ms.openlocfilehash: 1487b5f47966cfcae0e47848dae99b39b42db18d
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496255"
---
### <a name="keytips-behavior-improved-in-wpf"></a><span data-ttu-id="257e7-101">WPF での KeyTip の動作が改良された</span><span class="sxs-lookup"><span data-stu-id="257e7-101">Keytips behavior improved in WPF</span></span>

#### <a name="details"></a><span data-ttu-id="257e7-102">説明</span><span class="sxs-lookup"><span data-stu-id="257e7-102">Details</span></span>

<span data-ttu-id="257e7-103">KeyTip の動作が、Microsoft Word やエクスプローラーでの動作と同等に変更されています。</span><span class="sxs-lookup"><span data-stu-id="257e7-103">Keytips behavior has been modified to bring parity with behavior on Microsoft Word and Windows Explorer.</span></span> <span data-ttu-id="257e7-104"><xref:System.Windows.Input.KeyEventArgs.SystemKey> (具体的には <xref:System.Windows.Input.Key> または <xref:System.Windows.Input.Key.F11>) が押された場合に KeyTip の状態が有効かどうかを調べることによって、WPF は KeyTip キーを適切に処理します。</span><span class="sxs-lookup"><span data-stu-id="257e7-104">By checking whether keytip state is enabled or not in the case of a <xref:System.Windows.Input.KeyEventArgs.SystemKey> (in particular, <xref:System.Windows.Input.Key> or <xref:System.Windows.Input.Key.F11>) being pressed, WPF handles keytip keys appropriately.</span></span> <span data-ttu-id="257e7-105">メニューがマウスによって開かれている場合でも、KeyTip はメニューを閉じるようになっています。</span><span class="sxs-lookup"><span data-stu-id="257e7-105">Keytips now dismiss a menu even when it is opened by mouse.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="257e7-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="257e7-106">Suggestion</span></span>

<span data-ttu-id="257e7-107">N/A</span><span class="sxs-lookup"><span data-stu-id="257e7-107">N/A</span></span>

| <span data-ttu-id="257e7-108">名前</span><span class="sxs-lookup"><span data-stu-id="257e7-108">Name</span></span>    | <span data-ttu-id="257e7-109">[値]</span><span class="sxs-lookup"><span data-stu-id="257e7-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="257e7-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="257e7-110">Scope</span></span>   |<span data-ttu-id="257e7-111">エッジ</span><span class="sxs-lookup"><span data-stu-id="257e7-111">Edge</span></span>|
|<span data-ttu-id="257e7-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="257e7-112">Version</span></span>|<span data-ttu-id="257e7-113">4.7.2</span><span class="sxs-lookup"><span data-stu-id="257e7-113">4.7.2</span></span>|
|<span data-ttu-id="257e7-114">種類</span><span class="sxs-lookup"><span data-stu-id="257e7-114">Type</span></span>|<span data-ttu-id="257e7-115">ランタイム</span><span class="sxs-lookup"><span data-stu-id="257e7-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="257e7-116">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="257e7-116">Affected APIs</span></span>

<span data-ttu-id="257e7-117">API 分析では検出できません。</span><span class="sxs-lookup"><span data-stu-id="257e7-117">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
