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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bf6bc73683a6c37ceaaffc635a58803b71c3b6cd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782760"
---
# <a name="icordebugruntimeunwindableframe-interface"></a><span data-ttu-id="3bcd3-102">ICorDebugRuntimeUnwindableFrame インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3bcd3-102">ICorDebugRuntimeUnwindableFrame Interface</span></span>
<span data-ttu-id="3bcd3-103">共通言語ランタイム (CLR: Common Language Runtime) でフレームをアンワインドする必要のあるアンマネージ メソッドに対してサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="3bcd3-103">Provides support for unmanaged methods that require the common language runtime (CLR) to unwind a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3bcd3-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="3bcd3-104">Remarks</span></span>  
 <span data-ttu-id="3bcd3-105">`ICorDebugRuntimeUnwindableFrame` ICorDebugFrame インターフェイスの特殊化されたバージョンです。</span><span class="sxs-lookup"><span data-stu-id="3bcd3-105">`ICorDebugRuntimeUnwindableFrame` is a specialized version of the ICorDebugFrame interface.</span></span> <span data-ttu-id="3bcd3-106">現在のスタックのフレームをアンワインドするランタイムを必要とする非管理対象のメソッドによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="3bcd3-106">It is used by unmanaged methods that require the runtime to unwind a frame on the current stack.</span></span> <span data-ttu-id="3bcd3-107">既存のアンワインド規則は機能せず、JIT コンパイル コードを使用しないためです。</span><span class="sxs-lookup"><span data-stu-id="3bcd3-107">Existing unwinding conventions do not work, because they do not use JIT-compiled code.</span></span> <span data-ttu-id="3bcd3-108">デバッガーでは、アンワインド可能のフレームを見てを使用する、 [icordebugstackwalk::next](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md)メソッドが、アンワインドは自体検査を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3bcd3-108">When the debugger sees an unwindable frame, it should use the [ICorDebugStackWalk::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md) method to unwind it, but it should perform inspection itself.</span></span> <span data-ttu-id="3bcd3-109">デバッガーを受信すると、 `ICorDebugRuntimeUnwindableFrame`、呼び出すことができます、 [icordebugstackwalk::getcontext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md)フレームのコンテキストを取得します。</span><span class="sxs-lookup"><span data-stu-id="3bcd3-109">When the debugger receives an `ICorDebugRuntimeUnwindableFrame`, it can call the [ICorDebugStackWalk::GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) method to retrieve the context of the frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3bcd3-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="3bcd3-110">Requirements</span></span>  
 <span data-ttu-id="3bcd3-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3bcd3-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3bcd3-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3bcd3-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3bcd3-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3bcd3-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3bcd3-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3bcd3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bcd3-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="3bcd3-115">See also</span></span>

- [<span data-ttu-id="3bcd3-116">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3bcd3-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="3bcd3-117">デバッグ</span><span class="sxs-lookup"><span data-stu-id="3bcd3-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
