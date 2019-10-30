---
title: ICorDebugRuntimeUnwindableFrame インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugUnwindableFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugUnwindableFrame
helpviewer_keywords:
- ICorDebugUnwindableFrame interface [.NET Framework debugging]
ms.assetid: cd6a3982-6ed3-4909-808d-a66055e813e0
topic_type:
- apiref
ms.openlocfilehash: 2902744b6af3c7b2bd4def73b04807ce3333a8a1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131886"
---
# <a name="icordebugruntimeunwindableframe-interface"></a><span data-ttu-id="e6914-102">ICorDebugRuntimeUnwindableFrame インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e6914-102">ICorDebugRuntimeUnwindableFrame Interface</span></span>
<span data-ttu-id="e6914-103">共通言語ランタイム (CLR: Common Language Runtime) でフレームをアンワインドする必要のあるアンマネージ メソッドに対してサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="e6914-103">Provides support for unmanaged methods that require the common language runtime (CLR) to unwind a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e6914-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="e6914-104">Remarks</span></span>  
 <span data-ttu-id="e6914-105">`ICorDebugRuntimeUnwindableFrame` は、テキストフレームインターフェイスの特殊なバージョンです。</span><span class="sxs-lookup"><span data-stu-id="e6914-105">`ICorDebugRuntimeUnwindableFrame` is a specialized version of the ICorDebugFrame interface.</span></span> <span data-ttu-id="e6914-106">これは、ランタイムが現在のスタック上のフレームをアンワインドする必要があるアンマネージメソッドによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="e6914-106">It is used by unmanaged methods that require the runtime to unwind a frame on the current stack.</span></span> <span data-ttu-id="e6914-107">既存のアンワインド規則は、JIT コンパイルコードを使用しないため、機能しません。</span><span class="sxs-lookup"><span data-stu-id="e6914-107">Existing unwinding conventions do not work, because they do not use JIT-compiled code.</span></span> <span data-ttu-id="e6914-108">デバッガーに unwindable フレームが表示された場合、そのフレームをアンワインドするには、[次](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md)のメソッドを使用する必要がありますが、検査自体を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6914-108">When the debugger sees an unwindable frame, it should use the [ICorDebugStackWalk::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md) method to unwind it, but it should perform inspection itself.</span></span> <span data-ttu-id="e6914-109">デバッガーは、`ICorDebugRuntimeUnwindableFrame`を受信すると、テキストフレームのコンテキストを取得するために、「 [GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) 」メソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="e6914-109">When the debugger receives an `ICorDebugRuntimeUnwindableFrame`, it can call the [ICorDebugStackWalk::GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) method to retrieve the context of the frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6914-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="e6914-110">Requirements</span></span>  
 <span data-ttu-id="e6914-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6914-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6914-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e6914-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e6914-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e6914-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e6914-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6914-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6914-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="e6914-115">See also</span></span>

- [<span data-ttu-id="e6914-116">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e6914-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="e6914-117">デバッグ</span><span class="sxs-lookup"><span data-stu-id="e6914-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
