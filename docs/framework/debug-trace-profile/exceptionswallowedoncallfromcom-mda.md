---
title: exceptionSwallowedOnCallFromCom MDA
ms.date: 03/30/2017
helpviewer_keywords:
- messages, informational
- informational messages
- managed debugging assistants (MDAs), exceptions
- exception handling, managed debugging assistants
- MDAs (managed debugging assistants), exceptions
- ExceptionSwallowedOnCallFromCOM MDA
ms.assetid: 55d6ab12-f251-4aab-aa64-aacbe9d9f974
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4f076cbc556c7d9feff8a226f050743cd7728622
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61874446"
---
# <a name="exceptionswallowedoncallfromcom-mda"></a><span data-ttu-id="8e20c-102">exceptionSwallowedOnCallFromCom MDA</span><span class="sxs-lookup"><span data-stu-id="8e20c-102">exceptionSwallowedOnCallFromCom MDA</span></span>
<span data-ttu-id="8e20c-103">アンマネージド HRESULT 戻り値の型を持たないメソッドを介して COM から呼び出された 共通言語ランタイム (CLR) コードから、例外がスローされると、`exceptionSwallowedOnCallFromCOM` マネージド デバッグ アシスタント (MDA) がアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="8e20c-103">The `exceptionSwallowedOnCallFromCOM` managed debugging assistant (MDA) is activated when an exception is thrown from common language runtime (CLR) code called from COM via a method that does not have an unmanaged HRESULT return type.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="8e20c-104">症状</span><span class="sxs-lookup"><span data-stu-id="8e20c-104">Symptoms</span></span>  
 <span data-ttu-id="8e20c-105">COM からマネージド コンポーネントを呼び出すと、値 FALSE または 0 が返されます。</span><span class="sxs-lookup"><span data-stu-id="8e20c-105">A call to a managed component from COM returns with a value of FALSE or 0.</span></span> <span data-ttu-id="8e20c-106">あるいは、メソッドの戻り値の型が void の場合、メソッド実行中に例外がスローされたという通知がない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8e20c-106">Alternatively, if the method has a void return type, there may be no indication that an exception was thrown during the execution of the method.</span></span> <span data-ttu-id="8e20c-107">この場合、例外は自動的にキャッチされ、COM 呼び出し元に実行が戻ります。</span><span class="sxs-lookup"><span data-stu-id="8e20c-107">In this case, the exception will be silently caught and execution will return to the COM caller.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="8e20c-108">原因</span><span class="sxs-lookup"><span data-stu-id="8e20c-108">Cause</span></span>  
 <span data-ttu-id="8e20c-109">例外がスローされましたが、それを報告する有効な方法がありません。</span><span class="sxs-lookup"><span data-stu-id="8e20c-109">An exception was thrown, but there is no valid way to report it.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="8e20c-110">解像度</span><span class="sxs-lookup"><span data-stu-id="8e20c-110">Resolution</span></span>  
 <span data-ttu-id="8e20c-111">情報提供専用です。必ずしもバグを示すものではありません。</span><span class="sxs-lookup"><span data-stu-id="8e20c-111">Informational only, not necessarily indicative of a bug.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="8e20c-112">ランタイムへの影響</span><span class="sxs-lookup"><span data-stu-id="8e20c-112">Effect on the Runtime</span></span>  
 <span data-ttu-id="8e20c-113">この MDA は CLR に影響しません。</span><span class="sxs-lookup"><span data-stu-id="8e20c-113">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="8e20c-114">自動的にキャッチされた例外を報告するだけです。</span><span class="sxs-lookup"><span data-stu-id="8e20c-114">It only reports data about silently caught exceptions.</span></span>  
  
## <a name="output"></a><span data-ttu-id="8e20c-115">出力</span><span class="sxs-lookup"><span data-stu-id="8e20c-115">Output</span></span>  
 <span data-ttu-id="8e20c-116">メソッド名、型名、例外メッセージが含まれている情報メッセージ。</span><span class="sxs-lookup"><span data-stu-id="8e20c-116">Informational message containing the method name, type name, and exception message.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="8e20c-117">構成</span><span class="sxs-lookup"><span data-stu-id="8e20c-117">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <exceptionSwallowedOnCallFromCom />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8e20c-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="8e20c-118">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="8e20c-119">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="8e20c-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="8e20c-120">相互運用マーシャリング</span><span class="sxs-lookup"><span data-stu-id="8e20c-120">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
