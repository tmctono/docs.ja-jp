---
title: ICorDebugILFrame::SetIP メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.SetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::SetIP
helpviewer_keywords:
- SetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::SetIP method [.NET Framework debugging]
ms.assetid: 23f38dc1-85e4-4263-9235-2d05bbb6a833
topic_type:
- apiref
ms.openlocfilehash: 466fe421f4ff3f8983159ccb38503b75551c87bd
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788554"
---
# <a name="icordebugilframesetip-method"></a><span data-ttu-id="7ce79-102">ICorDebugILFrame::SetIP メソッド</span><span class="sxs-lookup"><span data-stu-id="7ce79-102">ICorDebugILFrame::SetIP Method</span></span>
<span data-ttu-id="7ce79-103">命令ポインターを Microsoft 中間言語 (MSIL) コード内の指定されたオフセット位置に設定します。</span><span class="sxs-lookup"><span data-stu-id="7ce79-103">Sets the instruction pointer to the specified offset location in the Microsoft intermediate language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ce79-104">構文</span><span class="sxs-lookup"><span data-stu-id="7ce79-104">Syntax</span></span>  
  
```cpp  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ce79-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7ce79-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="7ce79-106">MSIL コード内のオフセット位置。</span><span class="sxs-lookup"><span data-stu-id="7ce79-106">The offset location in the MSIL code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7ce79-107">コメント</span><span class="sxs-lookup"><span data-stu-id="7ce79-107">Remarks</span></span>  
 <span data-ttu-id="7ce79-108">`SetIP` を呼び出すと、現在のスレッドのすべてのフレームとチェーンがすぐに無効になります。</span><span class="sxs-lookup"><span data-stu-id="7ce79-108">Calls to `SetIP` immediately invalidate all frames and chains for the current thread.</span></span> <span data-ttu-id="7ce79-109">`SetIP`の呼び出しの後にデバッガーがフレーム情報を必要とする場合は、新しいスタックトレースを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ce79-109">If the debugger needs frame information after a call to `SetIP`, it must perform a new stack trace.</span></span>  
  
 <span data-ttu-id="7ce79-110">[ICorDebug](icordebug-interface.md)は、スタックフレームを有効な状態のままにします。</span><span class="sxs-lookup"><span data-stu-id="7ce79-110">[ICorDebug](icordebug-interface.md) will attempt to keep the stack frame in a valid state.</span></span> <span data-ttu-id="7ce79-111">ただし、フレームが有効な状態であっても、初期化されていないローカル変数などの問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7ce79-111">However, even if the frame is in a valid state, there still may be problems such as uninitialized local variables.</span></span> <span data-ttu-id="7ce79-112">呼び出し元は、実行中のプログラムの一貫性を確保する役割を担います。</span><span class="sxs-lookup"><span data-stu-id="7ce79-112">The caller is responsible for ensuring the coherency of the running program.</span></span>  
  
 <span data-ttu-id="7ce79-113">64ビットプラットフォームでは、命令ポインターを `catch` または `finally` ブロックの外に移動することはできません。</span><span class="sxs-lookup"><span data-stu-id="7ce79-113">On 64-bit platforms, the instruction pointer cannot be moved out of a `catch` or `finally` block.</span></span> <span data-ttu-id="7ce79-114">64ビットプラットフォーム上でこのような移動を行うために `SetIP` を呼び出すと、失敗を示す HRESULT が返されます。</span><span class="sxs-lookup"><span data-stu-id="7ce79-114">If `SetIP` is called to make such a move on a 64-bit platform, it will return an HRESULT indicating failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ce79-115">要件</span><span class="sxs-lookup"><span data-stu-id="7ce79-115">Requirements</span></span>  
 <span data-ttu-id="7ce79-116">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ce79-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ce79-117">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7ce79-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7ce79-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ce79-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ce79-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ce79-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
