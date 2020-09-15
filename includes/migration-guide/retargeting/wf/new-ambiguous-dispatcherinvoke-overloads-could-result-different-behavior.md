---
ms.openlocfilehash: 80e61d4dd5b8d4754a39e95e37475fefff57fcbd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617172"
---
### <a name="new-ambiguous-dispatcherinvoke-overloads-could-result-in-different-behavior"></a><span data-ttu-id="9fc88-101">新しい (あいまいな) Dispatcher.Invoke オーバーロードが、異なる動作になる可能性がある</span><span class="sxs-lookup"><span data-stu-id="9fc88-101">New (ambiguous) Dispatcher.Invoke overloads could result in different behavior</span></span>

#### <a name="details"></a><span data-ttu-id="9fc88-102">説明</span><span class="sxs-lookup"><span data-stu-id="9fc88-102">Details</span></span>

<span data-ttu-id="9fc88-103">.NET Framework 4.5 では、<xref:System.Action> 型のパラメーターを含む <xref:System.Windows.Threading.Dispatcher.Invoke%2A?displayProperty=nameWithType> に新しいオーバーロードが追加されます。</span><span class="sxs-lookup"><span data-stu-id="9fc88-103">The .NET Framework 4.5 adds new overloads to <xref:System.Windows.Threading.Dispatcher.Invoke%2A?displayProperty=nameWithType> that include a parameter of type <xref:System.Action>.</span></span> <span data-ttu-id="9fc88-104">既存のコードを再コンパイルすると、コンパイラは、<xref:System.Delegate> パラメーターを持つ Dispatcher.Invoke メソッドの呼び出しを、<xref:System.Action> パラメーターを持つ Dispatcher.Invoke メソッドの呼び出しとして解決することができます。</span><span class="sxs-lookup"><span data-stu-id="9fc88-104">When existing code is recompiled, compilers may resolve calls to Dispatcher.Invoke methods that have a <xref:System.Delegate> parameter as calls to Dispatcher.Invoke methods with an <xref:System.Action> parameter.</span></span> <span data-ttu-id="9fc88-105"><xref:System.Delegate> パラメーターを持つ Dispatcher.Invoke オーバーロードの呼び出しが <xref:System.Action> パラメーターを持つ Dispatcher.Invoke オーバーロードの呼び出しとして解決された場合、次のような動作の差異が生じることがあります。</span><span class="sxs-lookup"><span data-stu-id="9fc88-105">If a call to a Dispatcher.Invoke overload with a  <xref:System.Delegate> parameter is resolved as a call to a Dispatcher.Invoke overload with an <xref:System.Action> parameter, the following differences in behavior may occur:</span></span>

- <span data-ttu-id="9fc88-106">例外が発生した場合、<xref:System.Windows.Threading.Dispatcher.UnhandledExceptionFilter> イベントと <xref:System.Windows.Threading.Dispatcher.UnhandledException> イベントは発生しません。</span><span class="sxs-lookup"><span data-stu-id="9fc88-106">If an exception occurs, the <xref:System.Windows.Threading.Dispatcher.UnhandledExceptionFilter> and <xref:System.Windows.Threading.Dispatcher.UnhandledException> events are not raised.</span></span> <span data-ttu-id="9fc88-107">代わりに、例外は <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException?displayProperty=fullName> イベントによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="9fc88-107">Instead, exceptions are handled by the <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException?displayProperty=fullName> event.</span></span>
- <span data-ttu-id="9fc88-108"><xref:System.Windows.Threading.DispatcherOperation.Result> などの一部のメンバーの呼び出しは、操作が完了するまでブロックされます。</span><span class="sxs-lookup"><span data-stu-id="9fc88-108">Calls to some members, such as <xref:System.Windows.Threading.DispatcherOperation.Result>, block until the operation has completed.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="9fc88-109">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="9fc88-109">Suggestion</span></span>

<span data-ttu-id="9fc88-110">あいまいさ (および例外処理またはブロック動作における考えられる相違点) を回避するために、呼び出し元の Dispatcher.Invoke は Invoke 呼び出しの 2 番目のパラメーターとして空の object[] を渡すことで、.NET Framework 4.0 メソッドのオーバーロードに解決されるようにできます。</span><span class="sxs-lookup"><span data-stu-id="9fc88-110">To avoid ambiguity (and potential differences in exception handling or blocking behaviors), code calling Dispatcher.Invoke can pass an empty object[] as a second parameter to the Invoke call to be sure of resolving to the .NET Framework 4.0 method overload.</span></span>

| <span data-ttu-id="9fc88-111">名前</span><span class="sxs-lookup"><span data-stu-id="9fc88-111">Name</span></span>    | <span data-ttu-id="9fc88-112">[値]</span><span class="sxs-lookup"><span data-stu-id="9fc88-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="9fc88-113">スコープ</span><span class="sxs-lookup"><span data-stu-id="9fc88-113">Scope</span></span>   | <span data-ttu-id="9fc88-114">マイナー</span><span class="sxs-lookup"><span data-stu-id="9fc88-114">Minor</span></span>       |
| <span data-ttu-id="9fc88-115">バージョン</span><span class="sxs-lookup"><span data-stu-id="9fc88-115">Version</span></span> | <span data-ttu-id="9fc88-116">4.5</span><span class="sxs-lookup"><span data-stu-id="9fc88-116">4.5</span></span>         |
| <span data-ttu-id="9fc88-117">種類</span><span class="sxs-lookup"><span data-stu-id="9fc88-117">Type</span></span>    | <span data-ttu-id="9fc88-118">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="9fc88-118">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="9fc88-119">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="9fc88-119">Affected APIs</span></span>

- <xref:System.Windows.Threading.Dispatcher.Invoke(System.Delegate,System.Object[])?displayProperty=nameWithType>
- <xref:System.Windows.Threading.Dispatcher.Invoke(System.Delegate,System.TimeSpan,System.Object[])?displayProperty=nameWithType>
- <xref:System.Windows.Threading.Dispatcher.Invoke(System.Delegate,System.TimeSpan,System.Windows.Threading.DispatcherPriority,System.Object[])?displayProperty=nameWithType>
- <xref:System.Windows.Threading.Dispatcher.Invoke(System.Delegate,System.Windows.Threading.DispatcherPriority,System.Object[])?displayProperty=nameWithType>
