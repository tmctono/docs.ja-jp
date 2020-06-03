---
ms.openlocfilehash: fabbc9a51f61a703ce97db50ab251e7a13ffe348
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144483"
---
### <a name="countersetcreatecountersetinstance-now-throws-invalidoperationexception-if-instance-already-exists"></a><span data-ttu-id="c2d40-101">インスタンスが既に存在する場合、CounterSet.CreateCounterSetInstance は InvalidOperationException をスローするようになった</span><span class="sxs-lookup"><span data-stu-id="c2d40-101">CounterSet.CreateCounterSetInstance now throws InvalidOperationException if instance already exists</span></span>

<span data-ttu-id="c2d40-102">.NET 5.0 以降では、カウンター セットが既に存在する場合、<xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance(System.String)?displayProperty=nameWithType> は <xref:System.ArgumentException> ではなく <xref:System.InvalidOperationException> をスローします。</span><span class="sxs-lookup"><span data-stu-id="c2d40-102">Starting in .NET 5.0, <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance(System.String)?displayProperty=nameWithType> throws an <xref:System.InvalidOperationException> instead of an <xref:System.ArgumentException> if the counter set already exists.</span></span>

#### <a name="change-description"></a><span data-ttu-id="c2d40-103">変更の説明</span><span class="sxs-lookup"><span data-stu-id="c2d40-103">Change description</span></span>

<span data-ttu-id="c2d40-104">.NET Framework と .NET Core 1.0 から 3.1 では、<xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A> を呼び出すことによって、カウンター セットのインスタンスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c2d40-104">In .NET Framework and .NET Core 1.0 to 3.1, you can create an instance of the counter set by calling <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A>.</span></span> <span data-ttu-id="c2d40-105">ただし、カウンター セットが既に存在する場合、このメソッドは <xref:System.ArgumentException> 例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="c2d40-105">However, if the counter set already exists, the method throws an <xref:System.ArgumentException> exception.</span></span>

<span data-ttu-id="c2d40-106">.NET 5.0 以降のバージョンでは、<xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A> を呼び出したときにカウンター セットが存在すると、<xref:System.InvalidOperationException> 例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="c2d40-106">In .NET 5.0 and later versions, when you call <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A> and the counter set exists, an <xref:System.InvalidOperationException> exception is thrown.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="c2d40-107">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="c2d40-107">Version introduced</span></span>

<span data-ttu-id="c2d40-108">5.0 Preview 5</span><span class="sxs-lookup"><span data-stu-id="c2d40-108">5.0 Preview 5</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="c2d40-109">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="c2d40-109">Recommended action</span></span>

<span data-ttu-id="c2d40-110"><xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A> を呼び出すときにアプリで <xref:System.ArgumentException> 例外をキャッチする場合は、<xref:System.InvalidOperationException> 例外もキャッチすることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="c2d40-110">If you catch <xref:System.ArgumentException> exceptions in your app when calling <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A>, consider also catching <xref:System.InvalidOperationException> exceptions.</span></span>

> [!NOTE]
> <span data-ttu-id="c2d40-111"><xref:System.ArgumentException> 例外をキャッチすることは推奨されません。</span><span class="sxs-lookup"><span data-stu-id="c2d40-111">Catching <xref:System.ArgumentException> exceptions is not recommended.</span></span>

#### <a name="category"></a><span data-ttu-id="c2d40-112">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="c2d40-112">Category</span></span>

<span data-ttu-id="c2d40-113">Core .NET ライブラリ</span><span class="sxs-lookup"><span data-stu-id="c2d40-113">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c2d40-114">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="c2d40-114">Affected APIs</span></span>

- <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance(System.String)`

-->
