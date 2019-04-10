---
title: invalidFunctionPointerInDelegate MDA
ms.date: 03/30/2017
helpviewer_keywords:
- invalidFunctionPointerInDelegate MDA
- managed debugging assistants (MDAs), invalid function pointer to delegates
- MDAs (managed debugging assistants), invalid function pointer to delegates
- function pointers, invalid
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
- invalid function pointers
ms.assetid: 99ae44f1-783e-49a9-9009-24f54bbd0f09
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cbb33d2cddab22ad2072354ba543d2cd6a60a668
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59218278"
---
# <a name="invalidfunctionpointerindelegate-mda"></a><span data-ttu-id="aaf16-102">invalidFunctionPointerInDelegate MDA</span><span class="sxs-lookup"><span data-stu-id="aaf16-102">invalidFunctionPointerInDelegate MDA</span></span>
<span data-ttu-id="aaf16-103">ネイティブ関数ポインターに対するデリゲートを作成するときに、無効な関数ポインターが渡されると、`invalidFunctionPointerInDelegate` マネージド デバッグ アシスタント (MDA) がアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="aaf16-103">The `invalidFunctionPointerInDelegate` managed debugging assistant (MDA) is activated when an invalid function pointer is passed in to construct a delegate over a native function pointer.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="aaf16-104">症状</span><span class="sxs-lookup"><span data-stu-id="aaf16-104">Symptoms</span></span>  
 <span data-ttu-id="aaf16-105">関数ポインターでデリゲートを使用すると、アクセス違反または予期しないメモリの破損が発生します。</span><span class="sxs-lookup"><span data-stu-id="aaf16-105">Access violations or unexpected memory corruption when using a delegate over a function pointer.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="aaf16-106">原因</span><span class="sxs-lookup"><span data-stu-id="aaf16-106">Cause</span></span>  
 <span data-ttu-id="aaf16-107">無効な関数ポインターが指定されました。</span><span class="sxs-lookup"><span data-stu-id="aaf16-107">An invalid function pointer was specified.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="aaf16-108">解像度</span><span class="sxs-lookup"><span data-stu-id="aaf16-108">Resolution</span></span>  
 <span data-ttu-id="aaf16-109">有効な関数ポインターを指定します。</span><span class="sxs-lookup"><span data-stu-id="aaf16-109">Specify a valid function pointer</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="aaf16-110">ランタイムへの影響</span><span class="sxs-lookup"><span data-stu-id="aaf16-110">Effect on the Runtime</span></span>  
 <span data-ttu-id="aaf16-111">この MDA は CLR に影響しません。</span><span class="sxs-lookup"><span data-stu-id="aaf16-111">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="aaf16-112">出力</span><span class="sxs-lookup"><span data-stu-id="aaf16-112">Output</span></span>  
 <span data-ttu-id="aaf16-113">無効な関数ポインター。</span><span class="sxs-lookup"><span data-stu-id="aaf16-113">The invalid function pointer.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="aaf16-114">構成</span><span class="sxs-lookup"><span data-stu-id="aaf16-114">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidFunctionPointerInDelegate />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="aaf16-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="aaf16-115">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="aaf16-116">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="aaf16-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="aaf16-117">相互運用マーシャリング</span><span class="sxs-lookup"><span data-stu-id="aaf16-117">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
