---
title: invalidVariant MDA
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid variant
- VARIANT type errors
- InvalidVariant MDA
- invalid VARIANT types
- managed debugging assistants (MDAs), invalid variant
ms.assetid: d273e070-d1b1-4a53-a9c7-7af837b04a3d
ms.openlocfilehash: 8d686621ae4aa087e1b4f4bea9df7fc3de758d40
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216268"
---
# <a name="invalidvariant-mda"></a><span data-ttu-id="dd459-102">invalidVariant MDA</span><span class="sxs-lookup"><span data-stu-id="dd459-102">invalidVariant MDA</span></span>
<span data-ttu-id="dd459-103">`invalidVariant` マネージド デバッグ アシスタント (MDA: Managed Debugging Assistant) は、ネイティブ コードまたはアンマネージド コードからマネージド コードへの呼び出し時に、無効な `VARIANT` 構造体が見つかるとアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="dd459-103">The `invalidVariant` managed debugging assistant (MDA) is activated when an invalid `VARIANT` structure is encountered during a call from native or unmanaged code to managed code.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="dd459-104">現象</span><span class="sxs-lookup"><span data-stu-id="dd459-104">Symptoms</span></span>  
 <span data-ttu-id="dd459-105">`VARIANT` からオブジェクトへのマーシャリングを含む、ネイティブ コードとマネージド コードの間の遷移中に、予期しない動作が発生します。</span><span class="sxs-lookup"><span data-stu-id="dd459-105">Unexpected behavior during a transition between native and managed code involving the marshaling of a `VARIANT` to an object.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="dd459-106">原因</span><span class="sxs-lookup"><span data-stu-id="dd459-106">Cause</span></span>  
 <span data-ttu-id="dd459-107">ネイティブ コードが、不適切な `VARIANT` 構造体をマネージド コードに渡しています。</span><span class="sxs-lookup"><span data-stu-id="dd459-107">Native code is passing a malformed `VARIANT` structure to managed code.</span></span>  <span data-ttu-id="dd459-108">ランタイムは、この `VARIANT` をオブジェクトにマーシャリングしようとし、`VARIANT` が有効でない場合に MDA がアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="dd459-108">The runtime attempts to marshal this `VARIANT` to an object and activates the MDA if the `VARIANT` is not valid.</span></span> <span data-ttu-id="dd459-109">無効な `VARIANT` には、`VARIANT` VT_EMPTY &#124; VT_BYREF の `VARTYPE` や、`VARIANT` VT_VARIANT の `VARTYPE` などがあります。</span><span class="sxs-lookup"><span data-stu-id="dd459-109">Examples of invalid `VARIANT`S include a `VARIANT` with `VARTYPE` VT_EMPTY &#124; VT_BYREF or a `VARIANT` with `VARTYPE` VT_VARIANT.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="dd459-110">解決策</span><span class="sxs-lookup"><span data-stu-id="dd459-110">Resolution</span></span>  
 <span data-ttu-id="dd459-111">`VARIANT` を渡すネイティブ コードまたはアンマネージ コードでは、`VARIANT` の形式と初期化が正しいことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd459-111">The native or unmanaged code passing the `VARIANT` must ensure that the `VARIANT` is correctly formed and initialized.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="dd459-112">ランタイムへの影響</span><span class="sxs-lookup"><span data-stu-id="dd459-112">Effect on the Runtime</span></span>  
 <span data-ttu-id="dd459-113">この MDA は、ランタイムの動作への影響はありません。</span><span class="sxs-lookup"><span data-stu-id="dd459-113">The MDA has no effect on the runtime's behavior.</span></span>  
  
## <a name="output"></a><span data-ttu-id="dd459-114">出力</span><span class="sxs-lookup"><span data-stu-id="dd459-114">Output</span></span>  
 <span data-ttu-id="dd459-115">無効な `VARIANT` がアンマネージド モジュールによりマネージド コードに渡されたことを、ランタイムが検出したことを示す MDA メッセージです。</span><span class="sxs-lookup"><span data-stu-id="dd459-115">An MDA message indicating that the runtime detected an invalid `VARIANT` passed to managed code by an unmanaged module.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="dd459-116">構成</span><span class="sxs-lookup"><span data-stu-id="dd459-116">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidVariant />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="dd459-117">参照</span><span class="sxs-lookup"><span data-stu-id="dd459-117">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="dd459-118">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="dd459-118">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="dd459-119">相互運用マーシャリング</span><span class="sxs-lookup"><span data-stu-id="dd459-119">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
