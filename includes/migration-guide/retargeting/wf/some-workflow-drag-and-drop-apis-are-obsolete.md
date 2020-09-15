---
ms.openlocfilehash: b6cb7edcd6bed50efdf59f3321320ac8cd1b1ab8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617225"
---
### <a name="some-workflow-drag-and-drop-apis-are-obsolete"></a><span data-ttu-id="193f5-101">一部の WorkFlow ドラッグ アンド ドロップ API が廃止されました</span><span class="sxs-lookup"><span data-stu-id="193f5-101">Some WorkFlow drag-and-drop APIs are obsolete</span></span>

#### <a name="details"></a><span data-ttu-id="193f5-102">説明</span><span class="sxs-lookup"><span data-stu-id="193f5-102">Details</span></span>

<span data-ttu-id="193f5-103">この WorkFlow ドラッグ アンド ドロップ API は廃止され、アプリが 4.5 向けにリビルドされた場合、コンパイラ警告が発生します。</span><span class="sxs-lookup"><span data-stu-id="193f5-103">This WorkFlow drag-and-drop API is obsolete and will cause compiler warnings if the app is rebuilt against 4.5.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="193f5-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="193f5-104">Suggestion</span></span>

<span data-ttu-id="193f5-105">複数オブジェクトでの操作をサポートする新しい <xref:System.Activities.Presentation.DragDropHelper?displayProperty=fullName> API を代わりに使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="193f5-105">New <xref:System.Activities.Presentation.DragDropHelper?displayProperty=fullName> APIs that support operations with multiple objects should be used instead.</span></span> <span data-ttu-id="193f5-106">または、ビルド警告を抑制するか、古いコンパイラを使用して警告を回避できます。</span><span class="sxs-lookup"><span data-stu-id="193f5-106">Alternatively, the build warnings can be suppressed or they can be avoided by using an older compiler.</span></span> <span data-ttu-id="193f5-107">API は、まだサポートされています。</span><span class="sxs-lookup"><span data-stu-id="193f5-107">The APIs are still supported.</span></span>

| <span data-ttu-id="193f5-108">名前</span><span class="sxs-lookup"><span data-stu-id="193f5-108">Name</span></span>    | <span data-ttu-id="193f5-109">[値]</span><span class="sxs-lookup"><span data-stu-id="193f5-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="193f5-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="193f5-110">Scope</span></span>   | <span data-ttu-id="193f5-111">マイナー</span><span class="sxs-lookup"><span data-stu-id="193f5-111">Minor</span></span>       |
| <span data-ttu-id="193f5-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="193f5-112">Version</span></span> | <span data-ttu-id="193f5-113">4.5</span><span class="sxs-lookup"><span data-stu-id="193f5-113">4.5</span></span>         |
| <span data-ttu-id="193f5-114">種類</span><span class="sxs-lookup"><span data-stu-id="193f5-114">Type</span></span>    | <span data-ttu-id="193f5-115">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="193f5-115">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="193f5-116">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="193f5-116">Affected APIs</span></span>

- <xref:System.Activities.Presentation.DragDropHelper.DoDragMove(System.Activities.Presentation.WorkflowViewElement,System.Windows.Point)?displayProperty=nameWithType>
- <xref:System.Activities.Presentation.DragDropHelper.GetCompositeView(System.Windows.DragEventArgs)?displayProperty=nameWithType>
- <xref:System.Activities.Presentation.DragDropHelper.GetDraggedModelItem(System.Windows.DragEventArgs)?displayProperty=nameWithType>
- <xref:System.Activities.Presentation.DragDropHelper.GetDroppedObject(System.Windows.DependencyObject,System.Windows.DragEventArgs,System.Activities.Presentation.EditingContext)?displayProperty=nameWithType>
