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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 604486a074c3dbe3d19b741df28499ee03e1b2e5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59193279"
---
# <a name="icordebugnativeframesetip-method"></a><span data-ttu-id="35bf5-102">ICorDebugNativeFrame::SetIP メソッド</span><span class="sxs-lookup"><span data-stu-id="35bf5-102">ICorDebugNativeFrame::SetIP Method</span></span>
<span data-ttu-id="35bf5-103">命令ポインターをネイティブ コードで指定されたオフセット位置に設定します。</span><span class="sxs-lookup"><span data-stu-id="35bf5-103">Sets the instruction pointer to the specified offset location in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35bf5-104">構文</span><span class="sxs-lookup"><span data-stu-id="35bf5-104">Syntax</span></span>  
  
```  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35bf5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="35bf5-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="35bf5-106">[in]ネイティブ コード内のオフセット位置。</span><span class="sxs-lookup"><span data-stu-id="35bf5-106">[in] The offset location in the native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="35bf5-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="35bf5-107">Remarks</span></span>  
 <span data-ttu-id="35bf5-108">呼び出す`SetIP`すぐにすべてのフレームと現在のスレッドのチェーンが無効にします。</span><span class="sxs-lookup"><span data-stu-id="35bf5-108">Calls to `SetIP` immediately invalidate all frames and chains for the current thread.</span></span> <span data-ttu-id="35bf5-109">デバッガーには、呼び出しの後にフレーム情報が必要がある場合`SetIP`、新しいスタック トレースを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35bf5-109">If the debugger needs frame information after a call to `SetIP`, it must perform a new stack trace.</span></span>  
  
 <span data-ttu-id="35bf5-110">[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)有効な状態でスタック フレームを保持します。</span><span class="sxs-lookup"><span data-stu-id="35bf5-110">[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) will attempt to keep the stack frame in a valid state.</span></span> <span data-ttu-id="35bf5-111">ただし、場合でも、ランタイムがに関する限り、フレームは有効な状態では、まだある可能性があります、初期化されていないローカル変数などの問題。</span><span class="sxs-lookup"><span data-stu-id="35bf5-111">However, even if the frame is in a valid state, as far as the runtime is concerned, there still may be problems, such as uninitialized local variables, and so on.</span></span> <span data-ttu-id="35bf5-112">呼び出し元は、実行中のプログラムの一貫性を保証します。</span><span class="sxs-lookup"><span data-stu-id="35bf5-112">The caller is responsible for insuring coherency of the running program.</span></span>  
  
 <span data-ttu-id="35bf5-113">64 ビットのプラットフォームでのうち、命令ポインターを移動できません、`catch`または`finally`ブロックします。</span><span class="sxs-lookup"><span data-stu-id="35bf5-113">On 64-bit platforms, the instruction pointer cannot be moved out of a `catch` or `finally` block.</span></span> <span data-ttu-id="35bf5-114">場合`SetIP`というはエラーを示す HRESULT を返す、64 ビット プラットフォームで、このような移動するために、します。</span><span class="sxs-lookup"><span data-stu-id="35bf5-114">If `SetIP` is called to make such a move on a 64-bit platform, it will return an HRESULT indicating failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35bf5-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="35bf5-115">Requirements</span></span>  
 <span data-ttu-id="35bf5-116">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="35bf5-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35bf5-117">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="35bf5-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="35bf5-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="35bf5-118">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="35bf5-119">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="35bf5-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="35bf5-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="35bf5-120">See also</span></span>
