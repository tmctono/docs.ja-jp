---
title: invalidVariant MDA
description: InvalidVariant マネージデバッグアシスタントを確認します。これは、ネイティブ/アンマネージからマネージコードへの呼び出しで無効なバリアントが検出された場合に呼び出されます。
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid variant
- VARIANT type errors
- InvalidVariant MDA
- invalid VARIANT types
- managed debugging assistants (MDAs), invalid variant
ms.assetid: d273e070-d1b1-4a53-a9c7-7af837b04a3d
ms.openlocfilehash: ab1233d9faa86ef1508fa8fe2b5af46cb37bd523
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051637"
---
# <a name="invalidvariant-mda"></a><span data-ttu-id="92a41-103">invalidVariant MDA</span><span class="sxs-lookup"><span data-stu-id="92a41-103">invalidVariant MDA</span></span>
<span data-ttu-id="92a41-104">`invalidVariant` マネージド デバッグ アシスタント (MDA: Managed Debugging Assistant) は、ネイティブ コードまたはアンマネージド コードからマネージド コードへの呼び出し時に、無効な `VARIANT` 構造体が見つかるとアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="92a41-104">The `invalidVariant` managed debugging assistant (MDA) is activated when an invalid `VARIANT` structure is encountered during a call from native or unmanaged code to managed code.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="92a41-105">現象</span><span class="sxs-lookup"><span data-stu-id="92a41-105">Symptoms</span></span>  
 <span data-ttu-id="92a41-106">`VARIANT` からオブジェクトへのマーシャリングを含む、ネイティブ コードとマネージド コードの間の遷移中に、予期しない動作が発生します。</span><span class="sxs-lookup"><span data-stu-id="92a41-106">Unexpected behavior during a transition between native and managed code involving the marshaling of a `VARIANT` to an object.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="92a41-107">原因</span><span class="sxs-lookup"><span data-stu-id="92a41-107">Cause</span></span>  
 <span data-ttu-id="92a41-108">ネイティブ コードが、不適切な `VARIANT` 構造体をマネージド コードに渡しています。</span><span class="sxs-lookup"><span data-stu-id="92a41-108">Native code is passing a malformed `VARIANT` structure to managed code.</span></span>  <span data-ttu-id="92a41-109">ランタイムは、この `VARIANT` をオブジェクトにマーシャリングしようとし、`VARIANT` が有効でない場合に MDA がアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="92a41-109">The runtime attempts to marshal this `VARIANT` to an object and activates the MDA if the `VARIANT` is not valid.</span></span> <span data-ttu-id="92a41-110">無効な `VARIANT` には、`VARTYPE` VT_EMPTY &#124; VT_BYREF の `VARIANT` や、`VARTYPE` VT_VARIANT の `VARIANT` などがあります。</span><span class="sxs-lookup"><span data-stu-id="92a41-110">Examples of invalid `VARIANT`S include a `VARIANT` with `VARTYPE` VT_EMPTY &#124; VT_BYREF or a `VARIANT` with `VARTYPE` VT_VARIANT.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="92a41-111">解決方法</span><span class="sxs-lookup"><span data-stu-id="92a41-111">Resolution</span></span>  
 <span data-ttu-id="92a41-112">`VARIANT` を渡すネイティブ コードまたはアンマネージ コードでは、`VARIANT` の形式と初期化が正しいことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92a41-112">The native or unmanaged code passing the `VARIANT` must ensure that the `VARIANT` is correctly formed and initialized.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="92a41-113">ランタイムへの影響</span><span class="sxs-lookup"><span data-stu-id="92a41-113">Effect on the Runtime</span></span>  
 <span data-ttu-id="92a41-114">この MDA は、ランタイムの動作への影響はありません。</span><span class="sxs-lookup"><span data-stu-id="92a41-114">The MDA has no effect on the runtime's behavior.</span></span>  
  
## <a name="output"></a><span data-ttu-id="92a41-115">出力</span><span class="sxs-lookup"><span data-stu-id="92a41-115">Output</span></span>  
 <span data-ttu-id="92a41-116">無効な `VARIANT` がアンマネージド モジュールによりマネージド コードに渡されたことを、ランタイムが検出したことを示す MDA メッセージです。</span><span class="sxs-lookup"><span data-stu-id="92a41-116">An MDA message indicating that the runtime detected an invalid `VARIANT` passed to managed code by an unmanaged module.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="92a41-117">構成</span><span class="sxs-lookup"><span data-stu-id="92a41-117">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidVariant />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="92a41-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="92a41-118">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="92a41-119">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="92a41-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="92a41-120">相互運用マーシャリング</span><span class="sxs-lookup"><span data-stu-id="92a41-120">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
