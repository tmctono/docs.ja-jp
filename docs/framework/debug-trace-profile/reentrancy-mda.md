---
title: reentrancy MDA
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged code, debugging
- transitioning threads unmanaged to managed code
- reentrancy MDA
- reentrancy without an orderly transition
- managed debugging assistants (MDAs), reentrancy
- illegal reentrancy
- MDAs (managed debugging assistants), reentrancy
- threading [.NET Framework], managed debugging assistants
- managed code, debugging
- native debugging, MDAs
ms.assetid: 7240c3f3-7df8-4b03-bbf1-17cdce142d45
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3a1fb8a48cf6dbfc4edd6387fb35297c9c047270
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854040"
---
# <a name="reentrancy-mda"></a><span data-ttu-id="120bf-102">reentrancy MDA</span><span class="sxs-lookup"><span data-stu-id="120bf-102">reentrancy MDA</span></span>
<span data-ttu-id="120bf-103">`reentrancy` マネージド デバッグ アシスタント (MDA) は、前のマネージド コードからネイティブ コードへの切り替えが遷移順序を守って実行されなかった場合に、ネイティブ コードからマネージド コードへの遷移が試みられるとアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="120bf-103">The `reentrancy` managed debugging assistant (MDA) is activated when an attempt is made to transition from native to managed code in cases where a prior switch from managed to native code was not performed through an orderly transition.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="120bf-104">症状</span><span class="sxs-lookup"><span data-stu-id="120bf-104">Symptoms</span></span>  
 <span data-ttu-id="120bf-105">ネイティブ コードからマネージド コードに遷移するときに、オブジェクト ヒープが壊れたり、他の重大なエラーが発生しています。</span><span class="sxs-lookup"><span data-stu-id="120bf-105">The object heap is corrupted or other serious errors are occurring when transitioning from native to managed code.</span></span>  
  
 <span data-ttu-id="120bf-106">ネイティブ コードとマネージド コードの間でどちらかの方向に切り替えるスレッドは、適切な遷移順序を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="120bf-106">Threads that switch between native and managed code in either direction must perform an orderly transition.</span></span> <span data-ttu-id="120bf-107">ただし、ベクトル化例外ハンドラーなど、オペレーティング システムの特定の低レベル拡張ポイントでは、適切な遷移順序を実行しなくてもマネージド コードからネイティブ コードに切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="120bf-107">However, certain low-level extensibility points in the operating system, such as the vectored exception handler, allow switches from managed to native code without performing an orderly transition.</span></span>  <span data-ttu-id="120bf-108">これらの切り替えは、共通言語ランタイム (CLR) の管理下ではなく、オペレーティング システムの管理下にあります。</span><span class="sxs-lookup"><span data-stu-id="120bf-108">These switches are under operating system control, rather than under common language runtime (CLR) control.</span></span>  <span data-ttu-id="120bf-109">これらの拡張ポイント内で実行されるネイティブ コードでは、マネージド コードへのコールバックを避ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="120bf-109">Any native code that executes inside these extensibility points must avoid calling back into managed code.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="120bf-110">原因</span><span class="sxs-lookup"><span data-stu-id="120bf-110">Cause</span></span>  
 <span data-ttu-id="120bf-111">ベクトル化例外ハンドラーなどの低レベルのオペレーティング システム拡張ポイントは、マネージド コードの実行中にアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="120bf-111">A low-level operating system extensibility point, such as the vectored exception handler, has activated while executing managed code.</span></span>  <span data-ttu-id="120bf-112">そのような拡張ポイントを介して呼び出されたアプリケーション コードが、マネージド コードにコールバックしようとしています。</span><span class="sxs-lookup"><span data-stu-id="120bf-112">The application code that is invoked through that extensibility point is attempting to call back into managed code.</span></span>  
  
 <span data-ttu-id="120bf-113">この問題は常に、アプリケーション コードが原因で発生します。</span><span class="sxs-lookup"><span data-stu-id="120bf-113">This problem is always caused by application code.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="120bf-114">解決策</span><span class="sxs-lookup"><span data-stu-id="120bf-114">Resolution</span></span>  
 <span data-ttu-id="120bf-115">この MDA をアクティブにしたスレッドのスタック トレースを確認します。</span><span class="sxs-lookup"><span data-stu-id="120bf-115">Examine the stack trace for the thread that has activated this MDA.</span></span>  <span data-ttu-id="120bf-116">スレッドがマネージド コードの不正な呼び出しを試みています。</span><span class="sxs-lookup"><span data-stu-id="120bf-116">The thread is attempting to illegally call into managed code.</span></span>  <span data-ttu-id="120bf-117">スタック トレースでは、この拡張ポイントを使っているアプリケーションのコード、この拡張ポイントを提供しているオペレーティング システムのコード、および拡張ポイントによって中断されたマネージド コードが、示されているはずです。</span><span class="sxs-lookup"><span data-stu-id="120bf-117">The stack trace should reveal the application code using this extensibility point, the operating system code that provides this extensibility point, and the managed code that was interrupted by the extensibility point.</span></span>  
  
 <span data-ttu-id="120bf-118">たとえば、ベクトル化例外ハンドラー内からのマネージド コードの呼び出しの試みによってアクティブ化された MDA が表示されます。</span><span class="sxs-lookup"><span data-stu-id="120bf-118">For example, you will see the MDA activated in an attempt to call managed code from inside a vectored exception handler.</span></span>  <span data-ttu-id="120bf-119">スタックには、オペレーティング システムの例外処理コードと、<xref:System.DivideByZeroException> や <xref:System.AccessViolationException> などの例外をトリガーするマネージド コードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="120bf-119">On the stack you will see the operating system exception handling code and some managed code triggering an exception such as a <xref:System.DivideByZeroException> or an <xref:System.AccessViolationException>.</span></span>  
  
 <span data-ttu-id="120bf-120">この例の正しい解決策は、アンマネージ コードでベクトル化例外ハンドラーを完全に実装することです。</span><span class="sxs-lookup"><span data-stu-id="120bf-120">In this example, the correct resolution is to implement the vectored exception handler completely in unmanaged code.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="120bf-121">ランタイムへの影響</span><span class="sxs-lookup"><span data-stu-id="120bf-121">Effect on the Runtime</span></span>  
 <span data-ttu-id="120bf-122">この MDA は CLR に影響しません。</span><span class="sxs-lookup"><span data-stu-id="120bf-122">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="120bf-123">Output</span><span class="sxs-lookup"><span data-stu-id="120bf-123">Output</span></span>  
 <span data-ttu-id="120bf-124">MDA は、無効な再入が試みられていることを報告します。</span><span class="sxs-lookup"><span data-stu-id="120bf-124">The MDA reports that illegal reentrancy is being attempted.</span></span>  <span data-ttu-id="120bf-125">これが発生している理由と、問題の解決方法を確認するには、スレッドのスタックを調べます。</span><span class="sxs-lookup"><span data-stu-id="120bf-125">Examine the thread's stack to determine why this is happening and how to correct the problem.</span></span> <span data-ttu-id="120bf-126">サンプルの出力を次に示します。</span><span class="sxs-lookup"><span data-stu-id="120bf-126">The following is sample output.</span></span>  
  
```output
Additional Information: Attempting to call into managed code without   
transitioning out first.  Do not attempt to run managed code inside   
low-level native extensibility points. Managed Debugging Assistant   
'Reentrancy' has detected a problem in 'D:\ConsoleApplication1\  
ConsoleApplication1\bin\Debug\ConsoleApplication1.vshost.exe'.  
```  
  
## <a name="configuration"></a><span data-ttu-id="120bf-127">構成</span><span class="sxs-lookup"><span data-stu-id="120bf-127">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <reentrancy />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="120bf-128">例</span><span class="sxs-lookup"><span data-stu-id="120bf-128">Example</span></span>  
 <span data-ttu-id="120bf-129">次のコード例では、<xref:System.AccessViolationException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="120bf-129">The following code example causes an <xref:System.AccessViolationException> to be thrown.</span></span>  <span data-ttu-id="120bf-130">ベクトル化例外処理をサポートする Windows のバージョンでは、これによりマネージド ベクトル化例外ハンドラーが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="120bf-130">On versions of Windows that support vectored exception handling, this will cause the managed vectored exception handler to be called.</span></span>  <span data-ttu-id="120bf-131">`reentrancy` MDA が有効にされている場合、オペレーティング システムのベクトル化例外処理サポート コードから `MyHandler` の呼び出しが試みられると、MDA がアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="120bf-131">If the `reentrancy` MDA is enabled, the MDA will activate during the attempted call to `MyHandler` from the operating system's vectored exception handling support code.</span></span>  
  
```csharp
using System;  
public delegate int ExceptionHandler(IntPtr ptrExceptionInfo);  
  
public class Reenter   
{  
    public static ExceptionHandler keepAlive;  
  
    [System.Runtime.InteropServices.DllImport("kernel32", ExactSpelling=true,   
        CharSet=System.Runtime.InteropServices.CharSet.Auto)]  
    public static extern IntPtr AddVectoredExceptionHandler(int bFirst,   
        ExceptionHandler handler);  
  
    static int MyHandler(IntPtr ptrExceptionInfo)   
    {  
        // EXCEPTION_CONTINUE_SEARCH  
        return 0;  
    }  
    void Run() {}  
  
    static void Main()   
    {  
        keepAlive = new ExceptionHandler(Reenter.MyHandler);  
        IntPtr ret = AddVectoredExceptionHandler(1, keepAlive);  
        try   
        {  
            // Dispatch on null should AV.  
            Reenter r = null;   
            r.Run();  
        }   
        catch { }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="120bf-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="120bf-132">See also</span></span>

- [<span data-ttu-id="120bf-133">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="120bf-133">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
