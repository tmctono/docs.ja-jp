---
ms.openlocfilehash: 9d0791f00db7d830fc5d327af30218a0bbfcb25f
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496631"
---
### <a name="change-in-behavior-for-taskwaitall-methods-with-time-out-arguments"></a><span data-ttu-id="6acf9-101">タイムアウト引数を持つ Task.WaitAll メソッドの動作の変更</span><span class="sxs-lookup"><span data-stu-id="6acf9-101">Change in behavior for Task.WaitAll methods with time-out arguments</span></span>

#### <a name="details"></a><span data-ttu-id="6acf9-102">説明</span><span class="sxs-lookup"><span data-stu-id="6acf9-102">Details</span></span>

<span data-ttu-id="6acf9-103">.NET Framework 4.5 では、<xref:System.Threading.Tasks.Task.WaitAll%2A?displayProperty=nameWithType> の動作が、より一貫性のあるものになりました。 .NET Framework 4 では、これらのメソッドの動作に一貫性がありませんでした。</span><span class="sxs-lookup"><span data-stu-id="6acf9-103"><xref:System.Threading.Tasks.Task.WaitAll%2A?displayProperty=nameWithType> behavior was made more consistent in .NET Framework 4.5.In the .NET Framework 4, these methods behaved inconsistently.</span></span> <span data-ttu-id="6acf9-104">タイムアウトの期限が切れたときに、メソッドを呼び出す前に完了した、またはキャンセルされたタスクが 1 つ以上ある場合、メソッドでは <xref:System.AggregateException?displayProperty=fullName> 例外がスローされていました。</span><span class="sxs-lookup"><span data-stu-id="6acf9-104">When the time-out expired, if one or more tasks were completed or canceled before the method call, the method threw an <xref:System.AggregateException?displayProperty=fullName> exception.</span></span> <span data-ttu-id="6acf9-105">タイムアウトの期限が切れると、メソッド呼び出しの前に完了またはキャンセルされたタスクはなかったが、メソッド呼び出し後に 1 つ以上のタスクがこれらの状態になると、メソッドは false を返しました。</span><span class="sxs-lookup"><span data-stu-id="6acf9-105">When the time-out expired, if no tasks were completed or canceled before the method call, but one or more tasks entered these states after the method call, the method returned false.</span></span><br/><br/><span data-ttu-id="6acf9-106">.NET Framework 4.5 では、これらのメソッドのオーバーロードは、タイムアウト期限が切れたときにタスクがまだ実行中であった場合は false を返し、入力タスクがキャンセルされ (メソッド呼び出しの前か後かに関わらず)、他に実行中のタスクがなかった場合に限り、<xref:System.AggregateException?displayProperty=fullName> 例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="6acf9-106">In the .NET Framework 4.5, these method overloads now return false if any tasks are still running when the time-out interval expired, and they throw an <xref:System.AggregateException?displayProperty=fullName> exception only if an input task was cancelled (regardless of whether it was before or after the method call) and no other tasks are still running.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="6acf9-107">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="6acf9-107">Suggestion</span></span>

<span data-ttu-id="6acf9-108"><xref:System.Threading.Tasks.Task.WaitAll%2A> 呼び出しが呼び出される前にキャンセルされたタスクを検出する手段として <xref:System.AggregateException?displayProperty=fullName> がキャッチされていた場合、.NET Framework 4.6 は、すべての待機中タスクがタイムアウトの前に完了した場合に限ってスローするため、そのコードは、代わりに <xref:System.Threading.Tasks.Task.IsCanceled%2A> プロパティによって同じ検出を行う必要があります (例: .Any(t =&gt; t.IsCanceled))。</span><span class="sxs-lookup"><span data-stu-id="6acf9-108">If an <xref:System.AggregateException?displayProperty=fullName> was being caught as a means of detecting a task that was cancelled prior to the <xref:System.Threading.Tasks.Task.WaitAll%2A> call being invoked, that code should instead do the same detection via the  <xref:System.Threading.Tasks.Task.IsCanceled%2A> property (for example: .Any(t =&gt; t.IsCanceled)) since .NET Framework 4.6 will only throw in that case if all awaited tasks are completed prior to the timeout.</span></span>

| <span data-ttu-id="6acf9-109">名前</span><span class="sxs-lookup"><span data-stu-id="6acf9-109">Name</span></span>    | <span data-ttu-id="6acf9-110">[値]</span><span class="sxs-lookup"><span data-stu-id="6acf9-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="6acf9-111">スコープ</span><span class="sxs-lookup"><span data-stu-id="6acf9-111">Scope</span></span>   |<span data-ttu-id="6acf9-112">マイナー</span><span class="sxs-lookup"><span data-stu-id="6acf9-112">Minor</span></span>|
|<span data-ttu-id="6acf9-113">バージョン</span><span class="sxs-lookup"><span data-stu-id="6acf9-113">Version</span></span>|<span data-ttu-id="6acf9-114">4.5</span><span class="sxs-lookup"><span data-stu-id="6acf9-114">4.5</span></span>|
|<span data-ttu-id="6acf9-115">種類</span><span class="sxs-lookup"><span data-stu-id="6acf9-115">Type</span></span>|<span data-ttu-id="6acf9-116">ランタイム</span><span class="sxs-lookup"><span data-stu-id="6acf9-116">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="6acf9-117">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="6acf9-117">Affected APIs</span></span>

- <xref:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.Int32)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.Int32,System.Threading.CancellationToken)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.TimeSpan)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.Int32)`
- `M:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.Int32,System.Threading.CancellationToken)`
- `M:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.TimeSpan)`

-->
