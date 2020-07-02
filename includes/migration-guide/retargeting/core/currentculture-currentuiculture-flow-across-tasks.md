---
ms.openlocfilehash: 78faa5f4008b41bac75c94ce09a58c8227e5b485
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614672"
---
### <a name="currentculture-and-currentuiculture-flow-across-tasks"></a><span data-ttu-id="1a89d-101">タスク全体の CurrentCulture と CurrentUICulture のフロー</span><span class="sxs-lookup"><span data-stu-id="1a89d-101">CurrentCulture and CurrentUICulture flow across tasks</span></span>

#### <a name="details"></a><span data-ttu-id="1a89d-102">説明</span><span class="sxs-lookup"><span data-stu-id="1a89d-102">Details</span></span>

<span data-ttu-id="1a89d-103">.NET Framework 4.6 より、非同期操作全体をフローする、スレッドの <xref:System.Threading.ExecutionContext?displayProperty=fullName> に <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> と <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName> が格納されます。その結果、<xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> または <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName> に対する変更は、後で非同期実行されるタスクで反映されます。</span><span class="sxs-lookup"><span data-stu-id="1a89d-103">Beginning in the .NET Framework 4.6, <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> and <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName> are stored in the thread's <xref:System.Threading.ExecutionContext?displayProperty=fullName>, which flows across asynchronous operations.This means that changes to <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> or <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName> will be reflected in tasks which are later run asynchronously.</span></span> <span data-ttu-id="1a89d-104">これは、すべての非同期タスクで <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> と <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName> がリセットされていた、以前のバージョンの .NET Framework の動作とは異なります。</span><span class="sxs-lookup"><span data-stu-id="1a89d-104">This is different from the behavior of previous .NET Framework versions (which would reset <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> and <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName> in all asynchronous tasks).</span></span>

#### <a name="suggestion"></a><span data-ttu-id="1a89d-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="1a89d-105">Suggestion</span></span>

<span data-ttu-id="1a89d-106">この変更の影響を受けるアプリでは、非同期タスクの最初の操作として任意の <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> または <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName> を明示的に設定することで問題を回避できます。</span><span class="sxs-lookup"><span data-stu-id="1a89d-106">Apps affected by this change may work around it by explicitly setting the desired <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> or <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName> as the first operation in an async Task.</span></span> <span data-ttu-id="1a89d-107">あるいは、次の互換性スイッチを設定することで、<xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName>/<xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName> をフローしない以前の動作を選択できます。</span><span class="sxs-lookup"><span data-stu-id="1a89d-107">Alternatively, the old behavior (of not flowing <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName>/<xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName>) may be opted into by setting the following compatibility switch:</span></span>

```csharp
AppContext.SetSwitch("Switch.System.Globalization.NoAsyncCurrentCulture", true);
```

<span data-ttu-id="1a89d-108">この問題は、.NET Framework 4.6.2 の WPF で修正されました。</span><span class="sxs-lookup"><span data-stu-id="1a89d-108">This issue has been fixed by WPF in .NET Framework 4.6.2.</span></span> <span data-ttu-id="1a89d-109">また、.NET Frameworks 4.6、4.6.1 では [KB 3139549](https://support.microsoft.com/kb/3139549) を通じて修正されました。</span><span class="sxs-lookup"><span data-stu-id="1a89d-109">It has also been fixed in .NET Frameworks 4.6, 4.6.1 through [KB 3139549](https://support.microsoft.com/kb/3139549).</span></span> <span data-ttu-id="1a89d-110">.NET Framework 4.6 以降を対象とするアプリケーションでは WPF アプリケーション (<xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName>/<xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName>) の正しい動作が自動的に取得されます。これは、ディスパッチャー操作にわたって維持されます。</span><span class="sxs-lookup"><span data-stu-id="1a89d-110">Applications targeting .NET Framework 4.6 or later will automatically get the right behavior in WPF applications - <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName>/<xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName>) would be preserved across Dispatcher operations.</span></span>

| <span data-ttu-id="1a89d-111">名前</span><span class="sxs-lookup"><span data-stu-id="1a89d-111">Name</span></span>    | <span data-ttu-id="1a89d-112">値</span><span class="sxs-lookup"><span data-stu-id="1a89d-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="1a89d-113">スコープ</span><span class="sxs-lookup"><span data-stu-id="1a89d-113">Scope</span></span>   | <span data-ttu-id="1a89d-114">マイナー</span><span class="sxs-lookup"><span data-stu-id="1a89d-114">Minor</span></span>       |
| <span data-ttu-id="1a89d-115">バージョン</span><span class="sxs-lookup"><span data-stu-id="1a89d-115">Version</span></span> | <span data-ttu-id="1a89d-116">4.6</span><span class="sxs-lookup"><span data-stu-id="1a89d-116">4.6</span></span>         |
| <span data-ttu-id="1a89d-117">種類</span><span class="sxs-lookup"><span data-stu-id="1a89d-117">Type</span></span>    | <span data-ttu-id="1a89d-118">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="1a89d-118">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="1a89d-119">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="1a89d-119">Affected APIs</span></span>

- <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=nameWithType>
- <xref:System.Threading.Thread.CurrentCulture?displayProperty=nameWithType>
- <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=nameWithType>
- <xref:System.Threading.Thread.CurrentUICulture?displayProperty=nameWithType>
