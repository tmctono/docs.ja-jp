---
title: invalidIUnknown MDA
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid IUnknown pointer
- InvalidIUnknown MDA
- invalid IUnknown pointers
- IUnknown pointers
- managed debugging assistants (MDAs), invalid IUnknown pointer
ms.assetid: c7924771-a16b-40fe-b337-ce51dcdf6a12
ms.openlocfilehash: 5df9a3f506d8c2de6f1a3125459adc2d59d510bf
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217363"
---
# <a name="invalidiunknown-mda"></a><span data-ttu-id="fd33c-102">invalidIUnknown MDA</span><span class="sxs-lookup"><span data-stu-id="fd33c-102">invalidIUnknown MDA</span></span>
<span data-ttu-id="fd33c-103">`invalidIUnknown` マネージド デバッグ アシスタント (MDA: Managed Debugging Assistant) は、無効な `IUnknown` ポインターがネイティブ コードからマネージド コードに渡されるとアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="fd33c-103">The `invalidIUnknown` managed debugging assistant (MDA) is activated when an invalid `IUnknown` pointer is passed to managed code from native code.</span></span> <span data-ttu-id="fd33c-104">`IUnknown` インターフェイスが照会されたときに、`IUnknown` は、成功したことを返すことができませんでした。</span><span class="sxs-lookup"><span data-stu-id="fd33c-104">The `IUnknown` fails to return success when queried for the `IUnknown` interface.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="fd33c-105">現象</span><span class="sxs-lookup"><span data-stu-id="fd33c-105">Symptoms</span></span>  
 <span data-ttu-id="fd33c-106">引数のマーシャリング中に COM インターフェイス ポインターをマーシャリングすると、予期しないエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="fd33c-106">An unexpected error occurs when marshaling a COM interface pointer during argument marshaling.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="fd33c-107">原因</span><span class="sxs-lookup"><span data-stu-id="fd33c-107">Cause</span></span>  
 <span data-ttu-id="fd33c-108">CLR に渡された COM インターフェイスで、`QueryInterface` の実装が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="fd33c-108">An incorrect `QueryInterface` implementation on the COM interface passed to the CLR.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="fd33c-109">解決策</span><span class="sxs-lookup"><span data-stu-id="fd33c-109">Resolution</span></span>  
 <span data-ttu-id="fd33c-110">`QueryInterface` の実装を修正します。</span><span class="sxs-lookup"><span data-stu-id="fd33c-110">Correct the `QueryInterface` implementation.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="fd33c-111">ランタイムへの影響</span><span class="sxs-lookup"><span data-stu-id="fd33c-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="fd33c-112">この MDA は CLR に影響しません。</span><span class="sxs-lookup"><span data-stu-id="fd33c-112">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="fd33c-113">出力</span><span class="sxs-lookup"><span data-stu-id="fd33c-113">Output</span></span>  
 <span data-ttu-id="fd33c-114">エラーの説明。</span><span class="sxs-lookup"><span data-stu-id="fd33c-114">The description of the error.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="fd33c-115">構成</span><span class="sxs-lookup"><span data-stu-id="fd33c-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidIUnknown />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fd33c-116">参照</span><span class="sxs-lookup"><span data-stu-id="fd33c-116">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="fd33c-117">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="fd33c-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="fd33c-118">相互運用マーシャリング</span><span class="sxs-lookup"><span data-stu-id="fd33c-118">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
