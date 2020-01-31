---
title: ICorDebugNativeFrame::SetIP メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.SetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::SetIP
helpviewer_keywords:
- ICorDebugNativeFrame::SetIP method [.NET Framework debugging]
- SetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 57784a51-c76d-48f8-9392-584d0e1946d9
topic_type:
- apiref
ms.openlocfilehash: bc33768e4155a0e272d3374d4c586c79ef2ff3fb
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792779"
---
# <a name="icordebugnativeframesetip-method"></a><span data-ttu-id="809aa-102">ICorDebugNativeFrame::SetIP メソッド</span><span class="sxs-lookup"><span data-stu-id="809aa-102">ICorDebugNativeFrame::SetIP Method</span></span>
<span data-ttu-id="809aa-103">命令ポインターをネイティブコード内の指定されたオフセット位置に設定します。</span><span class="sxs-lookup"><span data-stu-id="809aa-103">Sets the instruction pointer to the specified offset location in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="809aa-104">構文</span><span class="sxs-lookup"><span data-stu-id="809aa-104">Syntax</span></span>  
  
```cpp  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="809aa-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="809aa-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="809aa-106">からネイティブコード内のオフセット位置。</span><span class="sxs-lookup"><span data-stu-id="809aa-106">[in] The offset location in the native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="809aa-107">コメント</span><span class="sxs-lookup"><span data-stu-id="809aa-107">Remarks</span></span>  
 <span data-ttu-id="809aa-108">`SetIP` を呼び出すと、現在のスレッドのすべてのフレームとチェーンがすぐに無効になります。</span><span class="sxs-lookup"><span data-stu-id="809aa-108">Calls to `SetIP` immediately invalidate all frames and chains for the current thread.</span></span> <span data-ttu-id="809aa-109">`SetIP`の呼び出しの後にデバッガーがフレーム情報を必要とする場合は、新しいスタックトレースを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="809aa-109">If the debugger needs frame information after a call to `SetIP`, it must perform a new stack trace.</span></span>  
  
 <span data-ttu-id="809aa-110">[ICorDebug](icordebug-interface.md)は、スタックフレームを有効な状態のままにします。</span><span class="sxs-lookup"><span data-stu-id="809aa-110">[ICorDebug](icordebug-interface.md) will attempt to keep the stack frame in a valid state.</span></span> <span data-ttu-id="809aa-111">ただし、フレームが有効な状態の場合でも、ランタイムの場合と同様に、初期化されていないローカル変数などの問題がまだ発生している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="809aa-111">However, even if the frame is in a valid state, as far as the runtime is concerned, there still may be problems, such as uninitialized local variables, and so on.</span></span> <span data-ttu-id="809aa-112">呼び出し元は、実行中のプログラムの一貫性を保証する役割を担います。</span><span class="sxs-lookup"><span data-stu-id="809aa-112">The caller is responsible for insuring coherency of the running program.</span></span>  
  
 <span data-ttu-id="809aa-113">64ビットプラットフォームでは、命令ポインターを `catch` または `finally` ブロックの外に移動することはできません。</span><span class="sxs-lookup"><span data-stu-id="809aa-113">On 64-bit platforms, the instruction pointer cannot be moved out of a `catch` or `finally` block.</span></span> <span data-ttu-id="809aa-114">64ビットプラットフォーム上でこのような移動を行うために `SetIP` を呼び出すと、失敗を示す HRESULT が返されます。</span><span class="sxs-lookup"><span data-stu-id="809aa-114">If `SetIP` is called to make such a move on a 64-bit platform, it will return an HRESULT indicating failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="809aa-115">要件</span><span class="sxs-lookup"><span data-stu-id="809aa-115">Requirements</span></span>  
 <span data-ttu-id="809aa-116">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="809aa-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="809aa-117">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="809aa-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="809aa-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="809aa-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="809aa-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="809aa-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="809aa-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="809aa-120">See also</span></span>
