---
title: invalidFunctionPointerInDelegate MDA
description: Invalidfunctionpointer Indelegate マネージデバッグアシスタント (MDA) を確認します。これは、デリゲートを作成するために無効な関数ポインターが渡された場合に呼び出されます。
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
ms.openlocfilehash: a17427d117c62ba782af3c9549c84623a3013b06
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051741"
---
# <a name="invalidfunctionpointerindelegate-mda"></a><span data-ttu-id="66bde-103">invalidFunctionPointerInDelegate MDA</span><span class="sxs-lookup"><span data-stu-id="66bde-103">invalidFunctionPointerInDelegate MDA</span></span>
<span data-ttu-id="66bde-104">ネイティブ関数ポインターに対するデリゲートを作成するときに、無効な関数ポインターが渡されると、`invalidFunctionPointerInDelegate` マネージド デバッグ アシスタント (MDA) がアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="66bde-104">The `invalidFunctionPointerInDelegate` managed debugging assistant (MDA) is activated when an invalid function pointer is passed in to construct a delegate over a native function pointer.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="66bde-105">現象</span><span class="sxs-lookup"><span data-stu-id="66bde-105">Symptoms</span></span>  
 <span data-ttu-id="66bde-106">関数ポインターでデリゲートを使用すると、アクセス違反または予期しないメモリの破損が発生します。</span><span class="sxs-lookup"><span data-stu-id="66bde-106">Access violations or unexpected memory corruption when using a delegate over a function pointer.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="66bde-107">原因</span><span class="sxs-lookup"><span data-stu-id="66bde-107">Cause</span></span>  
 <span data-ttu-id="66bde-108">無効な関数ポインターが指定されました。</span><span class="sxs-lookup"><span data-stu-id="66bde-108">An invalid function pointer was specified.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="66bde-109">解決方法</span><span class="sxs-lookup"><span data-stu-id="66bde-109">Resolution</span></span>  
 <span data-ttu-id="66bde-110">有効な関数ポインターを指定します。</span><span class="sxs-lookup"><span data-stu-id="66bde-110">Specify a valid function pointer</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="66bde-111">ランタイムへの影響</span><span class="sxs-lookup"><span data-stu-id="66bde-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="66bde-112">この MDA は CLR に影響しません。</span><span class="sxs-lookup"><span data-stu-id="66bde-112">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="66bde-113">出力</span><span class="sxs-lookup"><span data-stu-id="66bde-113">Output</span></span>  
 <span data-ttu-id="66bde-114">無効な関数ポインター。</span><span class="sxs-lookup"><span data-stu-id="66bde-114">The invalid function pointer.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="66bde-115">構成</span><span class="sxs-lookup"><span data-stu-id="66bde-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidFunctionPointerInDelegate />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="66bde-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="66bde-116">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="66bde-117">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="66bde-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="66bde-118">相互運用マーシャリング</span><span class="sxs-lookup"><span data-stu-id="66bde-118">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
