---
title: ICorDebugManagedCallback2::Exception メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.Exception
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::Exception
helpviewer_keywords:
- ICorDebugManagedCallback2::Exception method [.NET Framework debugging]
- Exception method, ICorDebugManagedCallback2 interface [.NET Framework debugging]
ms.assetid: 78b0f14f-2fae-4e63-8412-4df119ee8468
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f8952b34781045089945e7e72e179e88300b5fdd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61942533"
---
# <a name="icordebugmanagedcallback2exception-method"></a><span data-ttu-id="e8861-102">ICorDebugManagedCallback2::Exception メソッド</span><span class="sxs-lookup"><span data-stu-id="e8861-102">ICorDebugManagedCallback2::Exception Method</span></span>
<span data-ttu-id="e8861-103">例外ハンドラーの検索が開始されたことをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="e8861-103">Notifies the debugger that a search for an exception handler has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8861-104">構文</span><span class="sxs-lookup"><span data-stu-id="e8861-104">Syntax</span></span>  
  
```  
HRESULT Exception (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFrame       *pFrame,  
    [in] ULONG32              nOffset,  
    [in] CorDebugExceptionCallbackType dwEventType,  
    [in] DWORD                dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8861-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e8861-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="e8861-106">[in]例外がスローされたスレッドを格納しているアプリケーション ドメインを表す ICorDebugAppDomain オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="e8861-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread on which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="e8861-107">[in]例外がスローされたスレッドを表す ICorDebugThread オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="e8861-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the exception was thrown.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="e8861-108">[in]によって決定されたように、フレームを表す ICorDebugFrame オブジェクトへのポインター、`dwEventType`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="e8861-108">[in] A pointer to an ICorDebugFrame object that represents a frame, as determined by the `dwEventType` parameter.</span></span> <span data-ttu-id="e8861-109">詳細については、「解説」セクションの表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8861-109">For more information, see the table in the Remarks section.</span></span>  
  
 `nOffset`  
 <span data-ttu-id="e8861-110">[in]によって決定される単位のオフセットを指定する整数、`dwEventType`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="e8861-110">[in] An integer that specifies an offset, as determined by the `dwEventType` parameter.</span></span> <span data-ttu-id="e8861-111">詳細については、「解説」セクションの表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8861-111">For more information, see the table in the Remarks section.</span></span>  
  
 `dwEventType`  
 <span data-ttu-id="e8861-112">[in]この例外コールバックの種類を指定する CorDebugExceptionCallbackType 列挙型の値。</span><span class="sxs-lookup"><span data-stu-id="e8861-112">[in] A value of the CorDebugExceptionCallbackType enumeration that specifies the type of this exception callback.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="e8861-113">[in]値、 [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md)例外に関する追加情報を指定する列挙体</span><span class="sxs-lookup"><span data-stu-id="e8861-113">[in] A value of the [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) enumeration that specifies additional information about the exception</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e8861-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="e8861-114">Remarks</span></span>  
 <span data-ttu-id="e8861-115">`Exception`例外処理プロセスの検索フェーズ中にさまざまな時点でコールバックが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="e8861-115">The `Exception` callback is called at various points during the search phase of the exception-handling process.</span></span> <span data-ttu-id="e8861-116">これは、呼び出すことができますよりも 1 回、例外のアンワインド中に。</span><span class="sxs-lookup"><span data-stu-id="e8861-116">That is, it can be called more than once while unwinding an exception.</span></span>  
  
 <span data-ttu-id="e8861-117">によって参照される ICorDebugThread オブジェクトから処理される例外を取得できる、`pThread`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="e8861-117">The exception being processed can be retrieved from the ICorDebugThread object referenced by the `pThread` parameter.</span></span>  
  
 <span data-ttu-id="e8861-118">特定のフレームとのオフセットによって決定されます、`dwEventType`パラメーターとして次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e8861-118">The particular frame and offset are determined by the `dwEventType` parameter as follows:</span></span>  
  
|<span data-ttu-id="e8861-119">`dwEventType` の値</span><span class="sxs-lookup"><span data-stu-id="e8861-119">Value of `dwEventType`</span></span>|<span data-ttu-id="e8861-120">`pFrame` の値</span><span class="sxs-lookup"><span data-stu-id="e8861-120">Value of `pFrame`</span></span>|<span data-ttu-id="e8861-121">`nOffset` の値</span><span class="sxs-lookup"><span data-stu-id="e8861-121">Value of `nOffset`</span></span>|  
|----------------------------|-----------------------|------------------------|  
|<span data-ttu-id="e8861-122">DEBUG_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="e8861-122">DEBUG_EXCEPTION_FIRST_CHANCE</span></span>|<span data-ttu-id="e8861-123">例外をスローしたフレーム。</span><span class="sxs-lookup"><span data-stu-id="e8861-123">The frame that threw the exception.</span></span>|<span data-ttu-id="e8861-124">フレーム内の命令ポインター。</span><span class="sxs-lookup"><span data-stu-id="e8861-124">The instruction pointer in the frame.</span></span>|  
|<span data-ttu-id="e8861-125">DEBUG_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="e8861-125">DEBUG_EXCEPTION_USER_FIRST_CHANCE</span></span>|<span data-ttu-id="e8861-126">スローされた例外のポイントに最も近いユーザー コード フレーム。</span><span class="sxs-lookup"><span data-stu-id="e8861-126">The user-code frame closest to the point of the thrown exception.</span></span>|<span data-ttu-id="e8861-127">フレーム内の命令ポインター。</span><span class="sxs-lookup"><span data-stu-id="e8861-127">The instruction pointer in the frame.</span></span>|  
|<span data-ttu-id="e8861-128">DEBUG_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="e8861-128">DEBUG_EXCEPTION_CATCH_HANDLER_FOUND</span></span>|<span data-ttu-id="e8861-129">このフレームは、catch ハンドラーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e8861-129">The frame that contains the catch handler.</span></span>|<span data-ttu-id="e8861-130">Catch ハンドラーの先頭の Microsoft intermediate language (MSIL) オフセット。</span><span class="sxs-lookup"><span data-stu-id="e8861-130">The Microsoft intermediate language (MSIL) offset of the beginning of the catch handler.</span></span>|  
|<span data-ttu-id="e8861-131">DEBUG_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="e8861-131">DEBUG_EXCEPTION_UNHANDLED</span></span>|<span data-ttu-id="e8861-132">NULL</span><span class="sxs-lookup"><span data-stu-id="e8861-132">NULL</span></span>|<span data-ttu-id="e8861-133">定義されていません。</span><span class="sxs-lookup"><span data-stu-id="e8861-133">Undefined.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e8861-134">必要条件</span><span class="sxs-lookup"><span data-stu-id="e8861-134">Requirements</span></span>  
 <span data-ttu-id="e8861-135">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8861-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8861-136">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e8861-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e8861-137">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e8861-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e8861-138">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8861-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8861-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="e8861-139">See also</span></span>

- [<span data-ttu-id="e8861-140">ICorDebugManagedCallback2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e8861-140">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="e8861-141">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e8861-141">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
