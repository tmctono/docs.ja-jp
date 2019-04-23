---
title: dllMainReturnsFalse MDA
ms.date: 03/30/2017
helpviewer_keywords:
- managed debugging assistants (MDAs), DllMain returns false
- DllMainReturnsFalse MDA
- DllMain function
- MDAs (managed debugging assistants), DllMain returns false
ms.assetid: e2abdd04-f571-4b97-8c16-2221b8588429
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fd987cea78d082eee26032d5f98a54dc0cd3e1d5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59072624"
---
# <a name="dllmainreturnsfalse-mda"></a><span data-ttu-id="c2e0f-102">dllMainReturnsFalse MDA</span><span class="sxs-lookup"><span data-stu-id="c2e0f-102">dllMainReturnsFalse MDA</span></span>
<span data-ttu-id="c2e0f-103">`dllMainReturnsFalse` マネージド デバッグ アシスタント (MDA) は、DLL_PROCESS_ATTACH が原因で呼び出されたユーザー アセンブリのマネージド `DllMain` 関数が FALSE を返す場合にアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="c2e0f-103">The `dllMainReturnsFalse` managed debugging assistant (MDA) is activated if the managed `DllMain` function of a user assembly, called with reason DLL_PROCESS_ATTACH, returns FALSE.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="c2e0f-104">症状</span><span class="sxs-lookup"><span data-stu-id="c2e0f-104">Symptoms</span></span>  
 <span data-ttu-id="c2e0f-105">`DllMain` 関数が、正しく実行されなかったことを示す FALSE を返しました。</span><span class="sxs-lookup"><span data-stu-id="c2e0f-105">The `DllMain` function returned FALSE, indicating that it did not execute properly.</span></span> <span data-ttu-id="c2e0f-106">`DllMain` 関数には通常、重要な初期化コードが含まれているため、これは原因不明の問題を引き起こす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c2e0f-106">This can cause undetermined issues because `DllMain` functions typically contain important initialization code.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="c2e0f-107">原因</span><span class="sxs-lookup"><span data-stu-id="c2e0f-107">Cause</span></span>  
 <span data-ttu-id="c2e0f-108">`DllMain` 関数は、ロード時の DLL 初期化の DLL_PROCESS_ATTACH が原因で呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="c2e0f-108">The `DllMain` function is called with reason DLL_PROCESS_ATTACH for DLL initialization upon load.</span></span> <span data-ttu-id="c2e0f-109">FALSE が返された場合は、その DLL 初期化が失敗したことを意味します。</span><span class="sxs-lookup"><span data-stu-id="c2e0f-109">If it returns FALSE, it means that DLL initialization failed.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="c2e0f-110">解像度</span><span class="sxs-lookup"><span data-stu-id="c2e0f-110">Resolution</span></span>  
 <span data-ttu-id="c2e0f-111">失敗した DLL の `DllMain` 関数のコードを分析し、初期化エラーの原因を特定します。</span><span class="sxs-lookup"><span data-stu-id="c2e0f-111">Analyze the code of the `DllMain` function of the failed DLL and identify the cause of the initialization failure.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="c2e0f-112">ランタイムへの影響</span><span class="sxs-lookup"><span data-stu-id="c2e0f-112">Effect on the Runtime</span></span>  
 <span data-ttu-id="c2e0f-113">この MDA は CLR に影響しません。</span><span class="sxs-lookup"><span data-stu-id="c2e0f-113">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="c2e0f-114">`DllMain` の戻り値に関するデータのみを報告します。</span><span class="sxs-lookup"><span data-stu-id="c2e0f-114">It only reports data about the return value for `DllMain`.</span></span>  
  
## <a name="output"></a><span data-ttu-id="c2e0f-115">出力</span><span class="sxs-lookup"><span data-stu-id="c2e0f-115">Output</span></span>  
 <span data-ttu-id="c2e0f-116">DLL_PROCESS_ATTACH が原因で呼び出された `DllMain` 関数で FALSE が返されたことを示すメッセージ。</span><span class="sxs-lookup"><span data-stu-id="c2e0f-116">A message indicating that a `DllMain` function, called for reason DLL_PROCESS_ATTACH, returned FALSE.</span></span> <span data-ttu-id="c2e0f-117">この MDA は、`DllMain` がマネージド コードで実装された場合にのみアクティブになることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c2e0f-117">Note that this MDA is activated only if `DllMain` is implemented in managed code.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="c2e0f-118">構成</span><span class="sxs-lookup"><span data-stu-id="c2e0f-118">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <dllMainReturnsFalse />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c2e0f-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="c2e0f-119">See also</span></span>

- [<span data-ttu-id="c2e0f-120">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="c2e0f-120">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
