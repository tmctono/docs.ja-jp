---
title: illegalPrepareConstrainedRegion MDA
ms.date: 03/30/2017
helpviewer_keywords:
- PrepareConstrainedRegions method
- managed debugging assistants (MDAs), illegal PrepareConstrainedRegions
- try/catch exception handling, managed debugging assistants
- IllegalPrepareConstrainedRegions MDA
- MDAs (managed debugging assistants), illegal PrepareConstrainedRegions
ms.assetid: 2f9b5031-f910-4e01-a196-f89eab313eaf
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 623aff91eb801b4b32fc180bd97ed3822ad7f163
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2019
ms.locfileid: "71052670"
---
# <a name="illegalprepareconstrainedregion-mda"></a><span data-ttu-id="6ad16-102">illegalPrepareConstrainedRegion MDA</span><span class="sxs-lookup"><span data-stu-id="6ad16-102">illegalPrepareConstrainedRegion MDA</span></span>
<span data-ttu-id="6ad16-103">`illegalPrepareConstrainedRegion` マネージド デバッグ アシスタント (MDA) は、<xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A?displayProperty=nameWithType> メソッドの呼び出しが、例外ハンドラーの `try` ステートメントの直前にない場合にアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="6ad16-103">The `illegalPrepareConstrainedRegion` managed debugging assistant (MDA) is activated when a <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A?displayProperty=nameWithType> method call does not immediately precede the `try` statement of the exception handler.</span></span> <span data-ttu-id="6ad16-104">この制限は、MSIL レベルであり、呼び出しと `try` の間でコメントなどのコードを生成しないソースの使用が許可されます。</span><span class="sxs-lookup"><span data-stu-id="6ad16-104">This restriction is at the MSIL level, so it is permissible to have non-code-generating source between the call and the `try`, such as comments.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="6ad16-105">症状</span><span class="sxs-lookup"><span data-stu-id="6ad16-105">Symptoms</span></span>  
 <span data-ttu-id="6ad16-106">そのように扱われず、単純な例外処理ブロック (`finally` または `catch`) として扱われる制約された実行領域 (CER)。</span><span class="sxs-lookup"><span data-stu-id="6ad16-106">A constrained execution region (CER) that is never treated as such, but as a simple exception handling block (`finally` or `catch`).</span></span> <span data-ttu-id="6ad16-107">その結果、メモリ不足の状態やスレッドの中止のときには領域は実行されません。</span><span class="sxs-lookup"><span data-stu-id="6ad16-107">As a consequence, the region does not run in the event of an out-of-memory condition or a thread abort.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="6ad16-108">原因</span><span class="sxs-lookup"><span data-stu-id="6ad16-108">Cause</span></span>  
 <span data-ttu-id="6ad16-109">CER の準備パターンが正しく実行されません。</span><span class="sxs-lookup"><span data-stu-id="6ad16-109">The preparation pattern for a CER is not followed correctly.</span></span>  <span data-ttu-id="6ad16-110">エラー イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="6ad16-110">This is an error event.</span></span> <span data-ttu-id="6ad16-111"><xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> ブロック`catch` 内で/ CERの導入として例外ハンドラーをマークするために使用されるメソッド呼び出しは、の直前に使用する必要があります。/ `finally` `fault` / `filter``try`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="6ad16-111">The <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> method call used to mark exception handlers as introducing a CER in their `catch`/`finally`/`fault`/`filter` blocks must be used immediately before the `try` statement.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="6ad16-112">解決策</span><span class="sxs-lookup"><span data-stu-id="6ad16-112">Resolution</span></span>  
 <span data-ttu-id="6ad16-113">`try`ステートメントの直前に <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> の呼び出しがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6ad16-113">Ensure that the call to <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> happens immediately before the `try` statement.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="6ad16-114">ランタイムへの影響</span><span class="sxs-lookup"><span data-stu-id="6ad16-114">Effect on the Runtime</span></span>  
 <span data-ttu-id="6ad16-115">この MDA は CLR に影響しません。</span><span class="sxs-lookup"><span data-stu-id="6ad16-115">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="6ad16-116">出力</span><span class="sxs-lookup"><span data-stu-id="6ad16-116">Output</span></span>  
 <span data-ttu-id="6ad16-117">MDA は、<xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> メソッドの呼び出し元の名前、MSIL のオフセット、および呼び出しが try ブロックの先頭の直前にないことを示すメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="6ad16-117">The MDA displays the name of the method calling the <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> method, the MSIL offset, and a message indicating the call does not immediately precede the beginning of the try block.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="6ad16-118">構成</span><span class="sxs-lookup"><span data-stu-id="6ad16-118">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <illegalPrepareConstrainedRegion/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="6ad16-119">例</span><span class="sxs-lookup"><span data-stu-id="6ad16-119">Example</span></span>  
 <span data-ttu-id="6ad16-120">次のコード例では、この MDA のアクティブ化の原因となるパターンを示します。</span><span class="sxs-lookup"><span data-stu-id="6ad16-120">The following code example demonstrates the pattern that causes this MDA to be activated.</span></span>  
  
```csharp
void MethodWithInvalidPCR()  
{  
    RuntimeHelpers.PrepareConstrainedRegions();  
    Object o = new Object();  
    try  
    {  
        …  
    }  
    finally  
    {  
        …  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="6ad16-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="6ad16-121">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>
- [<span data-ttu-id="6ad16-122">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="6ad16-122">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="6ad16-123">相互運用マーシャリング</span><span class="sxs-lookup"><span data-stu-id="6ad16-123">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
