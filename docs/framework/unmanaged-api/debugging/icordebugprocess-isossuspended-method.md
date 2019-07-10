---
title: ICorDebugProcess::IsOSSuspended メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.IsOSSuspended
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::IsOSSuspended
helpviewer_keywords:
- IsOSSuspended method [.NET Framework debugging]
- ICorDebugProcess::IsOSSuspended method [.NET Framework debugging]
ms.assetid: 83406cb2-5797-4402-872d-89c9516aefec
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 275f62c8211f71f067d310dd4b3af2ddb11e93d7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67755462"
---
# <a name="icordebugprocessisossuspended-method"></a><span data-ttu-id="3dc4d-102">ICorDebugProcess::IsOSSuspended メソッド</span><span class="sxs-lookup"><span data-stu-id="3dc4d-102">ICorDebugProcess::IsOSSuspended Method</span></span>
<span data-ttu-id="3dc4d-103">このプロセスを停止するデバッガーの結果として、指定したスレッドが中断されたかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="3dc4d-103">Gets a value that indicates whether the specified thread has been suspended as a result of the debugger stopping this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3dc4d-104">構文</span><span class="sxs-lookup"><span data-stu-id="3dc4d-104">Syntax</span></span>  
  
```cpp  
HRESULT IsOSSuspended(  
    [in]  DWORD threadID,  
    [out] BOOL  *pbSuspended);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3dc4d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3dc4d-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="3dc4d-106">[in]対象のスレッドの ID。</span><span class="sxs-lookup"><span data-stu-id="3dc4d-106">[in] The ID of thread in question.</span></span>  
  
 `pbSuspended`  
 <span data-ttu-id="3dc4d-107">[out]ブール値へのポインター`true`中断されている以外の場合、指定したスレッドがされている場合 \*`pbSuspended`は`false`します。</span><span class="sxs-lookup"><span data-stu-id="3dc4d-107">[out] A pointer to a Boolean value that is `true` if the specified thread has been suspended; otherwise \*`pbSuspended` is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3dc4d-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="3dc4d-108">Remarks</span></span>  
 <span data-ttu-id="3dc4d-109">指定したスレッドの Win32 中断回数でデバッガーがこのプロセスの停止の結果として、指定されたスレッドが中断されたときに 1 ずつインクリメントされます。</span><span class="sxs-lookup"><span data-stu-id="3dc4d-109">When the specified thread has been suspended as a result of the debugger stopping this process, the specified thread's Win32 suspend count is incremented by one.</span></span> <span data-ttu-id="3dc4d-110">デバッガー ユーザー インターフェイス (UI) が、オペレーティング システムに表示される場合は、アカウントには、この情報を取得する可能性があります (OS) がユーザーに、スレッドの数を中断します。</span><span class="sxs-lookup"><span data-stu-id="3dc4d-110">The debugger user interface (UI) may want to take this information into account if it displays the operating system (OS) suspend count of the thread to the user.</span></span>  
  
 <span data-ttu-id="3dc4d-111">`IsOSSuspended`メソッドがアンマネージ デバッグのコンテキストでのみ意味します。</span><span class="sxs-lookup"><span data-stu-id="3dc4d-111">The `IsOSSuspended` method makes sense only in the context of unmanaged debugging.</span></span> <span data-ttu-id="3dc4d-112">マネージ デバッグ中のスレッドは協調的中断なく OS 中断です。</span><span class="sxs-lookup"><span data-stu-id="3dc4d-112">During managed debugging, threads are cooperatively suspended rather than OS-suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3dc4d-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="3dc4d-113">Requirements</span></span>  
 <span data-ttu-id="3dc4d-114">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3dc4d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3dc4d-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3dc4d-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3dc4d-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3dc4d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3dc4d-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3dc4d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
