---
title: pInvokeLog MDA
description: .NET での実行中に使用される一意のプラットフォーム呼び出しシグネチャごとにアクティブ化される pInvokeLog マネージデバッグアシスタント (MDA) について説明します。
ms.date: 03/30/2017
helpviewer_keywords:
- signatures, platform invoke
- MDAs (managed debugging assistants), platform invoke
- platform invoke, run-time errors
- platform invoke log
- PInvokeLog MDA
- managed debugging assistants (MDAs), platform invoke
ms.assetid: b830444a-5003-49fe-b89b-b8bee22f7b1a
ms.openlocfilehash: 05af4e17a91f7c0d8f3576a86d3d784ef6666aed
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803691"
---
# <a name="pinvokelog-mda"></a><span data-ttu-id="988bd-103">pInvokeLog MDA</span><span class="sxs-lookup"><span data-stu-id="988bd-103">pInvokeLog MDA</span></span>
<span data-ttu-id="988bd-104">`pInvokeLog` マネージド デバッグ アシスタント (MDA) は、実行中に使用される一意のプラットフォーム呼び出しシグネチャごとにアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="988bd-104">The `pInvokeLog` managed debugging assistant (MDA) is activated for each unique platform invoke signature used during execution.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="988bd-105">ランタイムへの影響</span><span class="sxs-lookup"><span data-stu-id="988bd-105">Effect on the Runtime</span></span>  
 <span data-ttu-id="988bd-106">この MDA は CLR に影響しません。</span><span class="sxs-lookup"><span data-stu-id="988bd-106">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="988bd-107">出力</span><span class="sxs-lookup"><span data-stu-id="988bd-107">Output</span></span>  
 <span data-ttu-id="988bd-108">実行中に使用されるプラットフォーム呼び出しシグネチャを示すメッセージ。</span><span class="sxs-lookup"><span data-stu-id="988bd-108">A message indicating the platform invoke signature used during execution.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="988bd-109">構成</span><span class="sxs-lookup"><span data-stu-id="988bd-109">Configuration</span></span>  
 <span data-ttu-id="988bd-110">各 match 要素で、プラットフォーム呼び出しが行われる .dll ファイルがフィルター処理されます。</span><span class="sxs-lookup"><span data-stu-id="988bd-110">Each match element filters the .dll files to which platform invoke calls are made.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="988bd-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="988bd-111">See also</span></span>

- [<span data-ttu-id="988bd-112">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="988bd-112">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="988bd-113">アンマネージ DLL 関数の処理</span><span class="sxs-lookup"><span data-stu-id="988bd-113">Consuming Unmanaged DLL Functions</span></span>](../interop/consuming-unmanaged-dll-functions.md)
