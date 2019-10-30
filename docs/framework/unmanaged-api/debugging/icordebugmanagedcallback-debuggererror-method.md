---
title: ICorDebugManagedCallback::DebuggerError メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.DebuggerError
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::DebuggerError
helpviewer_keywords:
- DebuggerError method [.NET Framework debugging]
- ICorDebugManagedCallback::DebuggerError method [.NET Framework debugging]
ms.assetid: 9e983d11-eaf3-4741-b936-29ec456384a3
topic_type:
- apiref
ms.openlocfilehash: c03be2405e1ab0287a2921b6e2e293862c67a193
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137373"
---
# <a name="icordebugmanagedcallbackdebuggererror-method"></a><span data-ttu-id="0c449-102">ICorDebugManagedCallback::DebuggerError メソッド</span><span class="sxs-lookup"><span data-stu-id="0c449-102">ICorDebugManagedCallback::DebuggerError Method</span></span>
<span data-ttu-id="0c449-103">共通言語ランタイム (CLR) からのイベントを処理しようとしたときに、エラーが発生したことをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="0c449-103">Notifies the debugger that an error has occurred while attempting to handle an event from the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c449-104">構文</span><span class="sxs-lookup"><span data-stu-id="0c449-104">Syntax</span></span>  
  
```cpp  
HRESULT DebuggerError (  
    [in] ICorDebugProcess *pProcess,  
    [in] HRESULT           errorHR,  
    [in] DWORD             errorCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c449-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0c449-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="0c449-106">からイベントが発生したプロセスを表す "いいプロセス" オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="0c449-106">[in] A pointer to an "ICorDebugProcess" object that represents the process in which the event occurred.</span></span>  
  
 `errorHR`  
 <span data-ttu-id="0c449-107">からイベントハンドラーから返された HRESULT 値。</span><span class="sxs-lookup"><span data-stu-id="0c449-107">[in] The HRESULT value that was returned from the event handler.</span></span>  
  
 `errorCode`  
 <span data-ttu-id="0c449-108">からCLR エラーを示す整数です。</span><span class="sxs-lookup"><span data-stu-id="0c449-108">[in] An integer that specifies the CLR error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c449-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="0c449-109">Remarks</span></span>  
 <span data-ttu-id="0c449-110">プロセスは、エラーの性質によっては、パススルーモードに配置される場合があります。</span><span class="sxs-lookup"><span data-stu-id="0c449-110">The process may be placed into pass-through mode, depending on the nature of the error.</span></span>  
  
 <span data-ttu-id="0c449-111">`DebugError` のコールバックは、エラーのためにデバッグサービスが無効になっていることを示します。そのため、デバッガーは、ユーザーがエラーメッセージを使用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c449-111">The `DebugError` callback indicates that debugging services have been disabled due to an error, so debuggers should make the error message available to the user.</span></span> <span data-ttu-id="0c449-112">[GetID:](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md) : ICorDebug は安全に呼び出すことができますが、他のすべてのメソッド ( [:: Terminate](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md)を含む) は呼び出さないでください。</span><span class="sxs-lookup"><span data-stu-id="0c449-112">[ICorDebugProcess::GetID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md) will be safe to call, but all other methods, including [ICorDebug::Terminate](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md), should not be called.</span></span> <span data-ttu-id="0c449-113">デバッガーでは、プロセスを終了するためにオペレーティングシステムの機能を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c449-113">The debugger should use operating-system facilities for terminating processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c449-114">［要件］</span><span class="sxs-lookup"><span data-stu-id="0c449-114">Requirements</span></span>  
 <span data-ttu-id="0c449-115">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c449-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c449-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0c449-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0c449-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0c449-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0c449-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c449-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c449-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="0c449-119">See also</span></span>

- [<span data-ttu-id="0c449-120">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0c449-120">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
