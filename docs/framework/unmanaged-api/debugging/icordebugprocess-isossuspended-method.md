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
ms.openlocfilehash: 039dc0d9befb038e643abc4e2524c133234f460b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775571"
---
# <a name="icordebugprocessisossuspended-method"></a><span data-ttu-id="a976c-102">ICorDebugProcess::IsOSSuspended メソッド</span><span class="sxs-lookup"><span data-stu-id="a976c-102">ICorDebugProcess::IsOSSuspended Method</span></span>
<span data-ttu-id="a976c-103">このプロセスを停止するデバッガーの結果として、指定したスレッドが中断されたかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="a976c-103">Gets a value that indicates whether the specified thread has been suspended as a result of the debugger stopping this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a976c-104">構文</span><span class="sxs-lookup"><span data-stu-id="a976c-104">Syntax</span></span>  
  
```  
HRESULT IsOSSuspended(  
    [in]  DWORD threadID,  
    [out] BOOL  *pbSuspended);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a976c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a976c-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="a976c-106">[in]対象のスレッドの ID。</span><span class="sxs-lookup"><span data-stu-id="a976c-106">[in] The ID of thread in question.</span></span>  
  
 `pbSuspended`  
 <span data-ttu-id="a976c-107">[out]ブール値へのポインター`true`中断されている以外の場合、指定したスレッドがされている場合 \*`pbSuspended`は`false`します。</span><span class="sxs-lookup"><span data-stu-id="a976c-107">[out] A pointer to a Boolean value that is `true` if the specified thread has been suspended; otherwise \*`pbSuspended` is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a976c-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="a976c-108">Remarks</span></span>  
 <span data-ttu-id="a976c-109">指定したスレッドの Win32 中断回数でデバッガーがこのプロセスの停止の結果として、指定されたスレッドが中断されたときに 1 ずつインクリメントされます。</span><span class="sxs-lookup"><span data-stu-id="a976c-109">When the specified thread has been suspended as a result of the debugger stopping this process, the specified thread's Win32 suspend count is incremented by one.</span></span> <span data-ttu-id="a976c-110">デバッガー ユーザー インターフェイス (UI) が、オペレーティング システムに表示される場合は、アカウントには、この情報を取得する可能性があります (OS) がユーザーに、スレッドの数を中断します。</span><span class="sxs-lookup"><span data-stu-id="a976c-110">The debugger user interface (UI) may want to take this information into account if it displays the operating system (OS) suspend count of the thread to the user.</span></span>  
  
 <span data-ttu-id="a976c-111">`IsOSSuspended`メソッドがアンマネージ デバッグのコンテキストでのみ意味します。</span><span class="sxs-lookup"><span data-stu-id="a976c-111">The `IsOSSuspended` method makes sense only in the context of unmanaged debugging.</span></span> <span data-ttu-id="a976c-112">マネージ デバッグ中のスレッドは協調的中断なく OS 中断です。</span><span class="sxs-lookup"><span data-stu-id="a976c-112">During managed debugging, threads are cooperatively suspended rather than OS-suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a976c-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="a976c-113">Requirements</span></span>  
 <span data-ttu-id="a976c-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a976c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a976c-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a976c-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a976c-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a976c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a976c-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a976c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
