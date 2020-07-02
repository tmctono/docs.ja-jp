---
ms.openlocfilehash: fc6066fd0b23d299158114cb397934041b99ba47
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620462"
---
### <a name="wpf-dispatchersynchronizationcontextcreatecopy-now-returns-a-new-copy-instead-of-the-current-instance"></a><span data-ttu-id="c1527-101">WPF DispatcherSynchronizationContext.CreateCopy は、現在のインスタンスの代わりに新しいコピーを返すようになった</span><span class="sxs-lookup"><span data-stu-id="c1527-101">WPF DispatcherSynchronizationContext.CreateCopy now returns a new copy instead of the current instance</span></span>

#### <a name="details"></a><span data-ttu-id="c1527-102">説明</span><span class="sxs-lookup"><span data-stu-id="c1527-102">Details</span></span>

<span data-ttu-id="c1527-103">.NET Framework 4 では、<xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> は、主にパフォーマンスの最適化として、現在のインスタンスへの参照を返しました。</span><span class="sxs-lookup"><span data-stu-id="c1527-103">In the .NET Framework 4, <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> returned a reference to the current instance, primarily as a performance optimization.</span></span> <span data-ttu-id="c1527-104">.NET Framework 4.5 では、これが新しいインスタンスになり、参照が等しければ、実行中のスレッドが正しい同期コンテキストにあると結論付けることが初めて可能になりました。</span><span class="sxs-lookup"><span data-stu-id="c1527-104">In the .NET Framework 4.5, it returns a new instance which makes it possible for the first time to conclude that equal references indicate the executing thread is in the correct synchronization context.</span></span>  <span data-ttu-id="c1527-105">これらの参照の ID をチェックするコードが影響を受ける可能性は低いですが、この変更により、<xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> を呼び出すコードは、.NET Framework 4.5 以降への移行の一部としてテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c1527-105">It is unlikely that code that checks the identity of these references will be affected, but because of the change, code that calls <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> should be tested as part of migration to the .NET Framework 4.5 or newer.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="c1527-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="c1527-106">Suggestion</span></span>

<span data-ttu-id="c1527-107"><xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> が新しい <xref:System.Threading.SynchronizationContext?displayProperty=fullName> オブジェクトを返すようになったことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c1527-107">Be aware that <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> will now return a new <xref:System.Threading.SynchronizationContext?displayProperty=fullName> object.</span></span> <span data-ttu-id="c1527-108">以前は、このように生成された参照の等価性を使用するコードは、実際には、正しいコンテキストにあるかどうかを確認していませんでしたが、.NET Framework 4.5 以降でのビルド時には確認を行います。</span><span class="sxs-lookup"><span data-stu-id="c1527-108">Previously, code that used equivalence of references generated this way was not actually checking whether it was in the proper context, but does when built against .NET Framework 4.5 or later.</span></span>  <span data-ttu-id="c1527-109">問題になる可能性は低いですが、影響を受けるコードのパスをよく調べて、何か問題が生じないかどうか確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c1527-109">While unlikely to cause issues, exercising the affected code paths should be enough to determine if this poses any problem.</span></span>

| <span data-ttu-id="c1527-110">名前</span><span class="sxs-lookup"><span data-stu-id="c1527-110">Name</span></span>    | <span data-ttu-id="c1527-111">[値]</span><span class="sxs-lookup"><span data-stu-id="c1527-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c1527-112">スコープ</span><span class="sxs-lookup"><span data-stu-id="c1527-112">Scope</span></span>   |<span data-ttu-id="c1527-113">マイナー</span><span class="sxs-lookup"><span data-stu-id="c1527-113">Minor</span></span>|
|<span data-ttu-id="c1527-114">バージョン</span><span class="sxs-lookup"><span data-stu-id="c1527-114">Version</span></span>|<span data-ttu-id="c1527-115">4.5</span><span class="sxs-lookup"><span data-stu-id="c1527-115">4.5</span></span>|
|<span data-ttu-id="c1527-116">種類</span><span class="sxs-lookup"><span data-stu-id="c1527-116">Type</span></span>|<span data-ttu-id="c1527-117">ランタイム</span><span class="sxs-lookup"><span data-stu-id="c1527-117">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c1527-118">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="c1527-118">Affected APIs</span></span>

-<xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy?displayProperty=nameWithType></li></ul>|
