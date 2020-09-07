---
ms.openlocfilehash: a806107456a65a4919592da9535a2617f677cfe0
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497904"
---
### <a name="wpf-dispatchersynchronizationcontextcreatecopy-now-returns-a-new-copy-instead-of-the-current-instance"></a><span data-ttu-id="65291-101">WPF DispatcherSynchronizationContext.CreateCopy は、現在のインスタンスの代わりに新しいコピーを返すようになった</span><span class="sxs-lookup"><span data-stu-id="65291-101">WPF DispatcherSynchronizationContext.CreateCopy now returns a new copy instead of the current instance</span></span>

#### <a name="details"></a><span data-ttu-id="65291-102">説明</span><span class="sxs-lookup"><span data-stu-id="65291-102">Details</span></span>

<span data-ttu-id="65291-103">.NET Framework 4 では、<xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> は、主にパフォーマンスの最適化として、現在のインスタンスへの参照を返しました。</span><span class="sxs-lookup"><span data-stu-id="65291-103">In the .NET Framework 4, <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> returned a reference to the current instance, primarily as a performance optimization.</span></span> <span data-ttu-id="65291-104">.NET Framework 4.5 では、これが新しいインスタンスになり、参照が等しければ、実行中のスレッドが正しい同期コンテキストにあると結論付けることが初めて可能になりました。</span><span class="sxs-lookup"><span data-stu-id="65291-104">In the .NET Framework 4.5, it returns a new instance which makes it possible for the first time to conclude that equal references indicate the executing thread is in the correct synchronization context.</span></span>  <span data-ttu-id="65291-105">これらの参照の ID をチェックするコードが影響を受ける可能性は低いですが、この変更により、<xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> を呼び出すコードは、.NET Framework 4.5 以降への移行の一部としてテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="65291-105">It is unlikely that code that checks the identity of these references will be affected, but because of the change, code that calls <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> should be tested as part of migration to the .NET Framework 4.5 or newer.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="65291-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="65291-106">Suggestion</span></span>

<span data-ttu-id="65291-107"><xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> が新しい <xref:System.Threading.SynchronizationContext?displayProperty=fullName> オブジェクトを返すようになったことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="65291-107">Be aware that <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> will now return a new <xref:System.Threading.SynchronizationContext?displayProperty=fullName> object.</span></span> <span data-ttu-id="65291-108">以前は、このように生成された参照の等価性を使用するコードは、実際には、正しいコンテキストにあるかどうかを確認していませんでしたが、.NET Framework 4.5 以降でのビルド時には確認を行います。</span><span class="sxs-lookup"><span data-stu-id="65291-108">Previously, code that used equivalence of references generated this way was not actually checking whether it was in the proper context, but does when built against .NET Framework 4.5 or later.</span></span>  <span data-ttu-id="65291-109">問題になる可能性は低いですが、影響を受けるコードのパスをよく調べて、何か問題が生じないかどうか確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65291-109">While unlikely to cause issues, exercising the affected code paths should be enough to determine if this poses any problem.</span></span>

| <span data-ttu-id="65291-110">名前</span><span class="sxs-lookup"><span data-stu-id="65291-110">Name</span></span>    | <span data-ttu-id="65291-111">[値]</span><span class="sxs-lookup"><span data-stu-id="65291-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="65291-112">スコープ</span><span class="sxs-lookup"><span data-stu-id="65291-112">Scope</span></span>   |<span data-ttu-id="65291-113">マイナー</span><span class="sxs-lookup"><span data-stu-id="65291-113">Minor</span></span>|
|<span data-ttu-id="65291-114">バージョン</span><span class="sxs-lookup"><span data-stu-id="65291-114">Version</span></span>|<span data-ttu-id="65291-115">4.5</span><span class="sxs-lookup"><span data-stu-id="65291-115">4.5</span></span>|
|<span data-ttu-id="65291-116">種類</span><span class="sxs-lookup"><span data-stu-id="65291-116">Type</span></span>|<span data-ttu-id="65291-117">ランタイム</span><span class="sxs-lookup"><span data-stu-id="65291-117">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="65291-118">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="65291-118">Affected APIs</span></span>

- <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy`

-->
