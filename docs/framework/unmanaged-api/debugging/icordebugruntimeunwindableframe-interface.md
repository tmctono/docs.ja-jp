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
ms.openlocfilehash: 26b0c78d5b34b920decc8c549d90ba8147e3f323
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791914"
---
# <a name="icordebugruntimeunwindableframe-interface"></a><span data-ttu-id="053a0-102">ICorDebugRuntimeUnwindableFrame インターフェイス</span><span class="sxs-lookup"><span data-stu-id="053a0-102">ICorDebugRuntimeUnwindableFrame Interface</span></span>
<span data-ttu-id="053a0-103">共通言語ランタイム (CLR: Common Language Runtime) でフレームをアンワインドする必要のあるアンマネージ メソッドに対してサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="053a0-103">Provides support for unmanaged methods that require the common language runtime (CLR) to unwind a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="053a0-104">コメント</span><span class="sxs-lookup"><span data-stu-id="053a0-104">Remarks</span></span>  
 <span data-ttu-id="053a0-105">`ICorDebugRuntimeUnwindableFrame` は、テキストフレームインターフェイスの特殊なバージョンです。</span><span class="sxs-lookup"><span data-stu-id="053a0-105">`ICorDebugRuntimeUnwindableFrame` is a specialized version of the ICorDebugFrame interface.</span></span> <span data-ttu-id="053a0-106">これは、ランタイムが現在のスタック上のフレームをアンワインドする必要があるアンマネージメソッドによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="053a0-106">It is used by unmanaged methods that require the runtime to unwind a frame on the current stack.</span></span> <span data-ttu-id="053a0-107">既存のアンワインド規則は、JIT コンパイルコードを使用しないため、機能しません。</span><span class="sxs-lookup"><span data-stu-id="053a0-107">Existing unwinding conventions do not work, because they do not use JIT-compiled code.</span></span> <span data-ttu-id="053a0-108">デバッガーに unwindable フレームが表示された場合、そのフレームをアンワインドするには、[次](icordebugstackwalk-next-method.md)のメソッドを使用する必要がありますが、検査自体を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="053a0-108">When the debugger sees an unwindable frame, it should use the [ICorDebugStackWalk::Next](icordebugstackwalk-next-method.md) method to unwind it, but it should perform inspection itself.</span></span> <span data-ttu-id="053a0-109">デバッガーは、`ICorDebugRuntimeUnwindableFrame`を受信すると、テキストフレームのコンテキストを取得するために、「 [GetContext](icordebugstackwalk-getcontext-method.md) 」メソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="053a0-109">When the debugger receives an `ICorDebugRuntimeUnwindableFrame`, it can call the [ICorDebugStackWalk::GetContext](icordebugstackwalk-getcontext-method.md) method to retrieve the context of the frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="053a0-110">要件</span><span class="sxs-lookup"><span data-stu-id="053a0-110">Requirements</span></span>  
 <span data-ttu-id="053a0-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="053a0-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="053a0-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="053a0-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="053a0-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="053a0-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="053a0-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="053a0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="053a0-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="053a0-115">See also</span></span>

- [<span data-ttu-id="053a0-116">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="053a0-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="053a0-117">デバッグ</span><span class="sxs-lookup"><span data-stu-id="053a0-117">Debugging</span></span>](index.md)
