---
ms.openlocfilehash: 58dbb54d42d89b450134758072e3133ae4e6b13d
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497585"
---
### <a name="systemthreadingtaskstask-no-longer-throw-objectdisposedexception-after-object-is-disposed"></a><span data-ttu-id="4e18d-101">System.Threading.Tasks.Task は、オブジェクトが破棄された後、ObjectDisposedException をスローしなくなりました</span><span class="sxs-lookup"><span data-stu-id="4e18d-101">System.Threading.Tasks.Task no longer throw ObjectDisposedException after object is disposed</span></span>

#### <a name="details"></a><span data-ttu-id="4e18d-102">説明</span><span class="sxs-lookup"><span data-stu-id="4e18d-102">Details</span></span>

<span data-ttu-id="4e18d-103"><xref:System.Threading.Tasks.Task.System%23IAsyncResult%23AsyncWaitHandle>を除き、<xref:System.Threading.Tasks.Task?displayProperty=fullName> メソッドでオブジェクトが破棄された後も <xref:System.ObjectDisposedException?displayProperty=fullName> の例外がスローされることがなくなりました。この変更により、キャッシュされたタスクを使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="4e18d-103">Except for <xref:System.Threading.Tasks.Task.System%23IAsyncResult%23AsyncWaitHandle>, <xref:System.Threading.Tasks.Task?displayProperty=fullName> methods no longer throw an <xref:System.ObjectDisposedException?displayProperty=fullName> exception after the object is disposed.This change supports the use of cached tasks.</span></span> <span data-ttu-id="4e18d-104">たとえば、メソッドで新しいタスクを割り当てる代わりに、既に完了した操作を表す、キャッシュされたタスクを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="4e18d-104">For example, a method can return a cached task to represent an already completed operation instead of allocating a new task.</span></span> <span data-ttu-id="4e18d-105">これは、タスクの任意のコンシューマーによって破棄されてしまうと、使用不可能になってしまう以前の .NET Framework のバージョンでは不可能でした。</span><span class="sxs-lookup"><span data-stu-id="4e18d-105">This was impossible in previous .NET Framework versions, because any consumer of the task could dispose of it, which rendered it unusable.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="4e18d-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="4e18d-106">Suggestion</span></span>

<span data-ttu-id="4e18d-107">オブジェクトが破棄されたとき、Task メソッドが <xref:System.ObjectDisposedException?displayProperty=fullName> をスローしなくなったことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4e18d-107">Be aware that Task methods may no longer throw <xref:System.ObjectDisposedException?displayProperty=fullName> in cases when the object is disposed.</span></span> <span data-ttu-id="4e18d-108">アプリが、タスクが破棄されたことを確認するために、この例外に依存していた場合は、<xref:System.Threading.Tasks.Task.Status> を使用してタスクのステータスを明示的に確認するように、アプリを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e18d-108">If an app was depending on this exception to know that a task was disposed, it should be updated to explicitly check the task's status using <xref:System.Threading.Tasks.Task.Status>.</span></span>

| <span data-ttu-id="4e18d-109">名前</span><span class="sxs-lookup"><span data-stu-id="4e18d-109">Name</span></span>    | <span data-ttu-id="4e18d-110">[値]</span><span class="sxs-lookup"><span data-stu-id="4e18d-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="4e18d-111">スコープ</span><span class="sxs-lookup"><span data-stu-id="4e18d-111">Scope</span></span>   |<span data-ttu-id="4e18d-112">マイナー</span><span class="sxs-lookup"><span data-stu-id="4e18d-112">Minor</span></span>|
|<span data-ttu-id="4e18d-113">バージョン</span><span class="sxs-lookup"><span data-stu-id="4e18d-113">Version</span></span>|<span data-ttu-id="4e18d-114">4.5</span><span class="sxs-lookup"><span data-stu-id="4e18d-114">4.5</span></span>|
|<span data-ttu-id="4e18d-115">種類</span><span class="sxs-lookup"><span data-stu-id="4e18d-115">Type</span></span>|<span data-ttu-id="4e18d-116">ランタイム</span><span class="sxs-lookup"><span data-stu-id="4e18d-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="4e18d-117">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="4e18d-117">Affected APIs</span></span>

<span data-ttu-id="4e18d-118">API 分析では検出できません。</span><span class="sxs-lookup"><span data-stu-id="4e18d-118">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
