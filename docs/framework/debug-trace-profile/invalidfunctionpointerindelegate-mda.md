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
ms.openlocfilehash: 6e3e64a720d12426fb066619b46c73402d1113e0
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2019
ms.locfileid: "71052628"
---
# <a name="invalidfunctionpointerindelegate-mda"></a><span data-ttu-id="ccd29-102">invalidFunctionPointerInDelegate MDA</span><span class="sxs-lookup"><span data-stu-id="ccd29-102">invalidFunctionPointerInDelegate MDA</span></span>
<span data-ttu-id="ccd29-103">ネイティブ関数ポインターに対するデリゲートを作成するときに、無効な関数ポインターが渡されると、`invalidFunctionPointerInDelegate` マネージド デバッグ アシスタント (MDA) がアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="ccd29-103">The `invalidFunctionPointerInDelegate` managed debugging assistant (MDA) is activated when an invalid function pointer is passed in to construct a delegate over a native function pointer.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="ccd29-104">症状</span><span class="sxs-lookup"><span data-stu-id="ccd29-104">Symptoms</span></span>  
 <span data-ttu-id="ccd29-105">関数ポインターでデリゲートを使用すると、アクセス違反または予期しないメモリの破損が発生します。</span><span class="sxs-lookup"><span data-stu-id="ccd29-105">Access violations or unexpected memory corruption when using a delegate over a function pointer.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="ccd29-106">原因</span><span class="sxs-lookup"><span data-stu-id="ccd29-106">Cause</span></span>  
 <span data-ttu-id="ccd29-107">無効な関数ポインターが指定されました。</span><span class="sxs-lookup"><span data-stu-id="ccd29-107">An invalid function pointer was specified.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="ccd29-108">解決策</span><span class="sxs-lookup"><span data-stu-id="ccd29-108">Resolution</span></span>  
 <span data-ttu-id="ccd29-109">有効な関数ポインターを指定します。</span><span class="sxs-lookup"><span data-stu-id="ccd29-109">Specify a valid function pointer</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="ccd29-110">ランタイムへの影響</span><span class="sxs-lookup"><span data-stu-id="ccd29-110">Effect on the Runtime</span></span>  
 <span data-ttu-id="ccd29-111">この MDA は CLR に影響しません。</span><span class="sxs-lookup"><span data-stu-id="ccd29-111">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="ccd29-112">出力</span><span class="sxs-lookup"><span data-stu-id="ccd29-112">Output</span></span>  
 <span data-ttu-id="ccd29-113">無効な関数ポインター。</span><span class="sxs-lookup"><span data-stu-id="ccd29-113">The invalid function pointer.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="ccd29-114">構成</span><span class="sxs-lookup"><span data-stu-id="ccd29-114">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidFunctionPointerInDelegate />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ccd29-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="ccd29-115">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="ccd29-116">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="ccd29-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="ccd29-117">相互運用マーシャリング</span><span class="sxs-lookup"><span data-stu-id="ccd29-117">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
