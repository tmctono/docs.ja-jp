---
ms.openlocfilehash: 85488de561a2298f2ff4009ec78b9a6e294053f3
ms.sourcegitcommit: 43d5aca3fda42bad8843f6c4e72f6bd52daa55f1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/09/2020
ms.locfileid: "89598174"
---
### <a name="threadabort-is-obsolete"></a><span data-ttu-id="01419-101">Thread.Abort は古い形式</span><span class="sxs-lookup"><span data-stu-id="01419-101">Thread.Abort is obsolete</span></span>

<span data-ttu-id="01419-102"><xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> API は非推奨になっています。</span><span class="sxs-lookup"><span data-stu-id="01419-102">The <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> APIs are obsolete.</span></span> <span data-ttu-id="01419-103">.NET 5.0 以降のバージョンを対象とするプロジェクトでは、これらのメソッドが呼び出されると、コンパイル時の警告が発生します。</span><span class="sxs-lookup"><span data-stu-id="01419-103">Projects that target .NET 5.0 or a later version will encounter compile-time warnings if these methods are called.</span></span> <span data-ttu-id="01419-104">警告を抑制すると、実行時に <xref:System.PlatformNotSupportedException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="01419-104">If you suppress the warnings, a <xref:System.PlatformNotSupportedException> will be thrown at run time.</span></span>

#### <a name="change-description"></a><span data-ttu-id="01419-105">変更内容</span><span class="sxs-lookup"><span data-stu-id="01419-105">Change description</span></span>

<span data-ttu-id="01419-106">以前は、<xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> を呼び出したときにコンパイル時の警告は生成されませんでしたが、このメソッドによって実行時に <xref:System.PlatformNotSupportedException> がスローされていました。</span><span class="sxs-lookup"><span data-stu-id="01419-106">Previously, calls to <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> did not produce compile-time warnings, however, the method did throw a <xref:System.PlatformNotSupportedException> at run time.</span></span>

<span data-ttu-id="01419-107">.NET 5.0 以降、<xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> は警告として古い形式を示すマークが付けられるようになりました。</span><span class="sxs-lookup"><span data-stu-id="01419-107">Starting in .NET 5.0, <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> is marked obsolete as warning.</span></span> <span data-ttu-id="01419-108">このメソッドを呼び出すと、コンパイラの警告 `SYSLIB0006` が生成されます。</span><span class="sxs-lookup"><span data-stu-id="01419-108">Calling this method produces compiler warning `SYSLIB0006`.</span></span> <span data-ttu-id="01419-109">メソッドの実装は変更されず、引き続き <xref:System.PlatformNotSupportedException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="01419-109">The implementation of the method is unchanged, and it continues to throw a <xref:System.PlatformNotSupportedException>.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="01419-110">変更理由</span><span class="sxs-lookup"><span data-stu-id="01419-110">Reason for change</span></span>

<span data-ttu-id="01419-111"><xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> により、.NET Framework を除くすべての .NET 実装で常に <xref:System.PlatformNotSupportedException> がスローされることを考慮して、呼び出される場所に注意を促すためにメソッドに <xref:System.ObsoleteAttribute> が追加されました。</span><span class="sxs-lookup"><span data-stu-id="01419-111">Given that <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> always throws a <xref:System.PlatformNotSupportedException> on all .NET implementations except .NET Framework, <xref:System.ObsoleteAttribute> was added to the method to draw attention to places where it's called.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="01419-112">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="01419-112">Version introduced</span></span>

<span data-ttu-id="01419-113">5.0 RC 1</span><span class="sxs-lookup"><span data-stu-id="01419-113">5.0 RC 1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="01419-114">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="01419-114">Recommended action</span></span>

- <span data-ttu-id="01419-115"><xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> を呼び出す代わりに、<xref:System.Threading.CancellationToken> を使用して作業単位の処理を中止します。</span><span class="sxs-lookup"><span data-stu-id="01419-115">Use a <xref:System.Threading.CancellationToken> to abort processing of a unit of work instead of calling <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="01419-116">次の例は、<xref:System.Threading.CancellationToken>の使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="01419-116">The following example illustrates the use of <xref:System.Threading.CancellationToken>.</span></span>

  ```csharp
  void ProcessPendingWorkItemsNew(CancellationToken cancellationToken)
  {
      if (QueryIsMoreWorkPending())
      {
          // If the CancellationToken is marked as "needs to cancel",
          // this will throw the appropriate exception.
          cancellationToken.ThrowIfCancellationRequested();

          WorkItem work = DequeueWorkItem();
          ProcessWorkItem(work);
      }
  }
  ```

  <span data-ttu-id="01419-117">詳細については、「[マネージド スレッドのキャンセル](../../../../docs/standard/threading/cancellation-in-managed-threads.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01419-117">For more information, see [Cancellation in managed threads](../../../../docs/standard/threading/cancellation-in-managed-threads.md).</span></span>

- <span data-ttu-id="01419-118">コンパイル時の警告が表示されないようにするには、警告コード `SYSLIB0006` を抑制します。</span><span class="sxs-lookup"><span data-stu-id="01419-118">To suppress the compile-time warning, suppress warning code `SYSLIB0006`.</span></span> <span data-ttu-id="01419-119">警告コードは <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> に固有であり、これを抑制しても、コード内の他の非推奨警告は抑制されません。</span><span class="sxs-lookup"><span data-stu-id="01419-119">The warning code is specific to <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> and suppressing it doesn't suppress other obsoletion warnings in your code.</span></span> <span data-ttu-id="01419-120">しかし、警告を抑制するのではなく、<xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> の呼び出しを削除することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="01419-120">However, we recommend that you remove calls to <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> instead of suppressing the warning.</span></span>

  ```csharp
  void MyMethod()
  {
  #pragma warning disable SYSLIB0006
      Thread.CurrentThread.Abort();
  #pragma warning restore SYSLIB0006
  }
  ```

  <span data-ttu-id="01419-121">また、プロジェクト ファイルで警告を抑制することもできます。</span><span class="sxs-lookup"><span data-stu-id="01419-121">You can also suppress the warning in the project file.</span></span>

  ```xml
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net5.0</TargetFramework>
    <!-- Disable "Thread.Abort is obsolete" warnings for entire project. -->
    <NoWarn>$(NoWarn);SYSLIB0006</NoWarn>
  </PropertyGroup>
  ```

#### <a name="category"></a><span data-ttu-id="01419-122">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="01419-122">Category</span></span>

- <span data-ttu-id="01419-123">Core .NET ライブラリ</span><span class="sxs-lookup"><span data-stu-id="01419-123">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="01419-124">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="01419-124">Affected APIs</span></span>

- <xref:System.Threading.Thread.Abort%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:System.Threading.Thread.Abort`

-->
