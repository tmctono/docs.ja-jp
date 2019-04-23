---
title: ICorDebugManagedCallback2::ExceptionUnwind メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.ExceptionUnwind
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::ExceptionUnwind
helpviewer_keywords:
- ICorDebugManagedCallback2::ExceptionUnwind method [.NET Framework debugging]
- ExceptionUnwind method [.NET Framework debugging]
ms.assetid: aaf5938d-179c-4eaa-8d35-8523a4fadded
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: faba9631e85ac84ff1517b64e9a3f5567ee7c9dc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59214795"
---
# <a name="icordebugmanagedcallback2exceptionunwind-method"></a><span data-ttu-id="7171e-102">ICorDebugManagedCallback2::ExceptionUnwind メソッド</span><span class="sxs-lookup"><span data-stu-id="7171e-102">ICorDebugManagedCallback2::ExceptionUnwind Method</span></span>
<span data-ttu-id="7171e-103">例外のアンワインド処理中に状態の通知を提供します。</span><span class="sxs-lookup"><span data-stu-id="7171e-103">Provides a status notification during the exception unwinding process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7171e-104">構文</span><span class="sxs-lookup"><span data-stu-id="7171e-104">Syntax</span></span>  
  
```  
HRESULT ExceptionUnwind (  
    [in] ICorDebugAppDomain                  *pAppDomain,  
    [in] ICorDebugThread                     *pThread,  
    [in] CorDebugExceptionUnwindCallbackType  dwEventType,  
    [in] DWORD                                dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7171e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7171e-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="7171e-106">[in]例外がスローされたスレッドを格納しているアプリケーション ドメインを表す ICorDebugAppDomain オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="7171e-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread on which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="7171e-107">[in]例外がスローされたスレッドを表す ICorDebugThread オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="7171e-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the exception was thrown.</span></span>  
  
 `dwEventType`  
 <span data-ttu-id="7171e-108">[in]アンワインド フェーズ中に、コールバックによって通知されるイベントを指定する CorDebugExceptionUnwindCallbackType 列挙型の値。</span><span class="sxs-lookup"><span data-stu-id="7171e-108">[in] A value of the CorDebugExceptionUnwindCallbackType enumeration that specifies the event that is being signaled by the callback during the unwind phase.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="7171e-109">[in]値、 [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md)例外に関する追加情報を指定する列挙体。</span><span class="sxs-lookup"><span data-stu-id="7171e-109">[in] A value of the [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) enumeration that specifies additional information about the exception.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7171e-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="7171e-110">Remarks</span></span>  
 <span data-ttu-id="7171e-111">`ExceptionUnwind` 例外処理プロセスのアンワインド フェーズ中にさまざまなポイントで呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="7171e-111">`ExceptionUnwind` is called at various points during the unwind phase of the exception-handling process.</span></span> <span data-ttu-id="7171e-112">`ExceptionUnwind` 1 つの例外のアンワインド中には複数回呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="7171e-112">`ExceptionUnwind` can be called more than once while unwinding a single exception.</span></span>  
  
 <span data-ttu-id="7171e-113">場合`dwEventType`DEBUG_EXCEPTION_INTERCEPTED、= の前にシーケンス ポイントで、スレッドのリーフ フレームで、命令ポインターになります (前にいくつかの手順でもかまいません) 例外の原因の命令。</span><span class="sxs-lookup"><span data-stu-id="7171e-113">If `dwEventType` = DEBUG_EXCEPTION_INTERCEPTED, the instruction pointer will be in the leaf frame of the thread, at the sequence point before (this may be several instructions before) the instruction that led to the exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7171e-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="7171e-114">Requirements</span></span>  
 <span data-ttu-id="7171e-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7171e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7171e-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7171e-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7171e-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7171e-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7171e-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7171e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7171e-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="7171e-119">See also</span></span>

- [<span data-ttu-id="7171e-120">ICorDebugManagedCallback2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7171e-120">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="7171e-121">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7171e-121">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
