---
ms.openlocfilehash: c557f1cb65a675446bc77c57ef91972df92712bb
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617159"
---
### <a name="iasyncresultcompletedsynchronously-property-must-be-correct-for-the-resulting-task-to-complete"></a><span data-ttu-id="d647c-101">IAsyncResult.CompletedSynchronously プロパティが正しくなければ、結果のタスクは完了しません</span><span class="sxs-lookup"><span data-stu-id="d647c-101">IAsyncResult.CompletedSynchronously property must be correct for the resulting task to complete</span></span>

#### <a name="details"></a><span data-ttu-id="d647c-102">説明</span><span class="sxs-lookup"><span data-stu-id="d647c-102">Details</span></span>

<span data-ttu-id="d647c-103">TaskFactory.FromAsync を呼び出すとき、<xref:System.IAsyncResult.CompletedSynchronously> プロパティの実装が正しくなければ、結果のタスクは完了しません。</span><span class="sxs-lookup"><span data-stu-id="d647c-103">When calling TaskFactory.FromAsync, the implementation of the <xref:System.IAsyncResult.CompletedSynchronously> property must be correct for the resulting task to complete.</span></span> <span data-ttu-id="d647c-104">つまり、実装が同期的に完了した場合にのみ、このプロパティは true を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="d647c-104">That is, the property must return true if, and only if, the implementation completed synchronously.</span></span> <span data-ttu-id="d647c-105">以前は、このプロパティは確認されていませんでした。</span><span class="sxs-lookup"><span data-stu-id="d647c-105">Previously, the property was not checked.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d647c-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="d647c-106">Suggestion</span></span>

<span data-ttu-id="d647c-107">タスクが同期的に完了したときにのみ、<xref:System.IAsyncResult?displayProperty=fullName> の実装が <xref:System.IAsyncResult.CompletedSynchronously?displayProperty=fullName> プロパティに true を返す場合、中断は発生しません。</span><span class="sxs-lookup"><span data-stu-id="d647c-107">If <xref:System.IAsyncResult?displayProperty=fullName> implementations correctly return true for the <xref:System.IAsyncResult.CompletedSynchronously?displayProperty=fullName> property only when a task completed synchronously, then no break will be observed.</span></span> <span data-ttu-id="d647c-108">ユーザーは、所有する <xref:System.IAsyncResult?displayProperty=fullName> の実装 (ある場合) を見直して、タスクが同期的に完了したかどうかを正しく評価することを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d647c-108">Users should review <xref:System.IAsyncResult?displayProperty=fullName> implementations they own (if any) to ensure that they correctly evaluate whether a task completed synchronously or not.</span></span>

| <span data-ttu-id="d647c-109">名前</span><span class="sxs-lookup"><span data-stu-id="d647c-109">Name</span></span>    | <span data-ttu-id="d647c-110">[値]</span><span class="sxs-lookup"><span data-stu-id="d647c-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d647c-111">スコープ</span><span class="sxs-lookup"><span data-stu-id="d647c-111">Scope</span></span>   | <span data-ttu-id="d647c-112">エッジ</span><span class="sxs-lookup"><span data-stu-id="d647c-112">Edge</span></span>        |
| <span data-ttu-id="d647c-113">バージョン</span><span class="sxs-lookup"><span data-stu-id="d647c-113">Version</span></span> | <span data-ttu-id="d647c-114">4.5</span><span class="sxs-lookup"><span data-stu-id="d647c-114">4.5</span></span>         |
| <span data-ttu-id="d647c-115">種類</span><span class="sxs-lookup"><span data-stu-id="d647c-115">Type</span></span>    | <span data-ttu-id="d647c-116">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="d647c-116">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="d647c-117">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="d647c-117">Affected APIs</span></span>

- <xref:System.Threading.Tasks.TaskFactory.FromAsync(System.IAsyncResult,System.Action{System.IAsyncResult})?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync(System.IAsyncResult,System.Action{System.IAsyncResult},System.Threading.Tasks.TaskCreationOptions)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync(System.IAsyncResult,System.Action{System.IAsyncResult},System.Threading.Tasks.TaskCreationOptions,System.Threading.Tasks.TaskScheduler)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601(System.IAsyncResult,System.Func{System.IAsyncResult,%60%600})?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync(System.Func{System.AsyncCallback,System.Object,System.IAsyncResult},System.Action{System.IAsyncResult},System.Object)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync(System.Func{System.AsyncCallback,System.Object,System.IAsyncResult},System.Action{System.IAsyncResult},System.Object,System.Threading.Tasks.TaskCreationOptions)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601(System.Func{%60%600,System.AsyncCallback,System.Object,System.IAsyncResult},System.Action{System.IAsyncResult},%60%600,System.Object)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601(System.Func{%60%600,System.AsyncCallback,System.Object,System.IAsyncResult},System.Action{System.IAsyncResult},%60%600,System.Object,System.Threading.Tasks.TaskCreationOptions)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601(System.Func{System.AsyncCallback,System.Object,System.IAsyncResult},System.Func{System.IAsyncResult,%60%600},System.Object)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601(System.Func{System.AsyncCallback,System.Object,System.IAsyncResult},System.Func{System.IAsyncResult,%60%600},System.Object,System.Threading.Tasks.TaskCreationOptions)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601(System.IAsyncResult,System.Func{System.IAsyncResult,%60%600},System.Threading.Tasks.TaskCreationOptions)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601(System.IAsyncResult,System.Func{System.IAsyncResult,%60%600},System.Threading.Tasks.TaskCreationOptions,System.Threading.Tasks.TaskScheduler)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602(System.Func{%60%600,%60%601,System.AsyncCallback,System.Object,System.IAsyncResult},System.Action{System.IAsyncResult},%60%600,%60%601,System.Object)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602(System.Func{%60%600,%60%601,System.AsyncCallback,System.Object,System.IAsyncResult},System.Action{System.IAsyncResult},%60%600,%60%601,System.Object,System.Threading.Tasks.TaskCreationOptions)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602(System.Func{%60%600,System.AsyncCallback,System.Object,System.IAsyncResult},System.Func{System.IAsyncResult,%60%601},%60%600,System.Object)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602(System.Func{%60%600,System.AsyncCallback,System.Object,System.IAsyncResult},System.Func{System.IAsyncResult,%60%601},%60%600,System.Object,System.Threading.Tasks.TaskCreationOptions)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603(System.Func{%60%600,%60%601,System.AsyncCallback,System.Object,System.IAsyncResult},System.Func{System.IAsyncResult,%60%602},%60%600,%60%601,System.Object)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603(System.Func{%60%600,%60%601,%60%602,System.AsyncCallback,System.Object,System.IAsyncResult},System.Action{System.IAsyncResult},%60%600,%60%601,%60%602,System.Object)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603(System.Func{%60%600,%60%601,%60%602,System.AsyncCallback,System.Object,System.IAsyncResult},System.Action{System.IAsyncResult},%60%600,%60%601,%60%602,System.Object,System.Threading.Tasks.TaskCreationOptions)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603(System.Func{%60%600,%60%601,System.AsyncCallback,System.Object,System.IAsyncResult},System.Func{System.IAsyncResult,%60%602},%60%600,%60%601,System.Object,System.Threading.Tasks.TaskCreationOptions)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%604(System.Func{%60%600,%60%601,%60%602,System.AsyncCallback,System.Object,System.IAsyncResult},System.Func{System.IAsyncResult,%60%603},%60%600,%60%601,%60%602,System.Object)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%604(System.Func{%60%600,%60%601,%60%602,System.AsyncCallback,System.Object,System.IAsyncResult},System.Func{System.IAsyncResult,%60%603},%60%600,%60%601,%60%602,System.Object,System.Threading.Tasks.TaskCreationOptions)?displayProperty=nameWithType>
