---
title: pInvokeLog MDA
ms.date: 03/30/2017
helpviewer_keywords:
- signatures, platform invoke
- MDAs (managed debugging assistants), platform invoke
- platform invoke, run-time errors
- platform invoke log
- PInvokeLog MDA
- managed debugging assistants (MDAs), platform invoke
ms.assetid: b830444a-5003-49fe-b89b-b8bee22f7b1a
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a7fe0b33bbd77143da6d2f4a26b170e4d7afe1fb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59104469"
---
# <a name="pinvokelog-mda"></a><span data-ttu-id="e3869-102">pInvokeLog MDA</span><span class="sxs-lookup"><span data-stu-id="e3869-102">pInvokeLog MDA</span></span>
<span data-ttu-id="e3869-103">`pInvokeLog` マネージド デバッグ アシスタント (MDA) は、実行中に使用される一意のプラットフォーム呼び出しシグネチャごとにアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="e3869-103">The `pInvokeLog` managed debugging assistant (MDA) is activated for each unique platform invoke signature used during execution.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="e3869-104">ランタイムへの影響</span><span class="sxs-lookup"><span data-stu-id="e3869-104">Effect on the Runtime</span></span>  
 <span data-ttu-id="e3869-105">この MDA は CLR に影響しません。</span><span class="sxs-lookup"><span data-stu-id="e3869-105">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="e3869-106">出力</span><span class="sxs-lookup"><span data-stu-id="e3869-106">Output</span></span>  
 <span data-ttu-id="e3869-107">実行中に使用されるプラットフォーム呼び出しシグネチャを示すメッセージ。</span><span class="sxs-lookup"><span data-stu-id="e3869-107">A message indicating the platform invoke signature used during execution.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="e3869-108">構成</span><span class="sxs-lookup"><span data-stu-id="e3869-108">Configuration</span></span>  
 <span data-ttu-id="e3869-109">各 match 要素で、プラットフォーム呼び出しが行われる .dll ファイルがフィルター処理されます。</span><span class="sxs-lookup"><span data-stu-id="e3869-109">Each match element filters the .dll files to which platform invoke calls are made.</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <pInvokeLog>  
      <filter>  
        <match dllName="user32.dll"/>  
        <match dllName="kernel32.dll"/>  
      </filter>  
    </pInvokeLog>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e3869-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="e3869-110">See also</span></span>

- [<span data-ttu-id="e3869-111">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="e3869-111">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="e3869-112">アンマネージ DLL 関数の処理</span><span class="sxs-lookup"><span data-stu-id="e3869-112">Consuming Unmanaged DLL Functions</span></span>](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)
