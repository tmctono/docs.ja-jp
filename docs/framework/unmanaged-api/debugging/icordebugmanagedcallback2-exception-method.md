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
ms.openlocfilehash: 612b63ba9aa3504cab5196932293946d486955ce
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210203"
---
# <a name="icordebugmanagedcallback2exception-method"></a><span data-ttu-id="acdfc-102">ICorDebugManagedCallback2::Exception メソッド</span><span class="sxs-lookup"><span data-stu-id="acdfc-102">ICorDebugManagedCallback2::Exception Method</span></span>
<span data-ttu-id="acdfc-103">例外ハンドラーの検索が開始されたことをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="acdfc-103">Notifies the debugger that a search for an exception handler has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acdfc-104">構文</span><span class="sxs-lookup"><span data-stu-id="acdfc-104">Syntax</span></span>  
  
```cpp  
HRESULT Exception (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFrame       *pFrame,  
    [in] ULONG32              nOffset,  
    [in] CorDebugExceptionCallbackType dwEventType,  
    [in] DWORD                dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="acdfc-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="acdfc-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="acdfc-106">から例外がスローされたスレッドを含むアプリケーションドメインを表す、のオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="acdfc-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread on which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="acdfc-107">から例外がスローされたスレッドを表す、スレッドオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="acdfc-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the exception was thrown.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="acdfc-108">からパラメーターによって決定される、フレームを表すテキストボックスオブジェクトへのポインター `dwEventType` 。</span><span class="sxs-lookup"><span data-stu-id="acdfc-108">[in] A pointer to an ICorDebugFrame object that represents a frame, as determined by the `dwEventType` parameter.</span></span> <span data-ttu-id="acdfc-109">詳細については、「解説」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="acdfc-109">For more information, see the table in the Remarks section.</span></span>  
  
 `nOffset`  
 <span data-ttu-id="acdfc-110">からパラメーターによって決定されるオフセットを指定する整数 `dwEventType` 。</span><span class="sxs-lookup"><span data-stu-id="acdfc-110">[in] An integer that specifies an offset, as determined by the `dwEventType` parameter.</span></span> <span data-ttu-id="acdfc-111">詳細については、「解説」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="acdfc-111">For more information, see the table in the Remarks section.</span></span>  
  
 `dwEventType`  
 <span data-ttu-id="acdfc-112">からこの例外コールバックの種類を指定する Cordebugexceptioncallback Type 列挙体の値。</span><span class="sxs-lookup"><span data-stu-id="acdfc-112">[in] A value of the CorDebugExceptionCallbackType enumeration that specifies the type of this exception callback.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="acdfc-113">から例外に関する追加情報を指定する[Cordebugexceptionflags](cordebugexceptionflags-enumeration.md)列挙値</span><span class="sxs-lookup"><span data-stu-id="acdfc-113">[in] A value of the [CorDebugExceptionFlags](cordebugexceptionflags-enumeration.md) enumeration that specifies additional information about the exception</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="acdfc-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="acdfc-114">Remarks</span></span>  
 <span data-ttu-id="acdfc-115">`Exception`コールバックは、例外処理プロセスの検索フェーズ中にさまざまなポイントで呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="acdfc-115">The `Exception` callback is called at various points during the search phase of the exception-handling process.</span></span> <span data-ttu-id="acdfc-116">つまり、例外のアンワインド中に複数回呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="acdfc-116">That is, it can be called more than once while unwinding an exception.</span></span>  
  
 <span data-ttu-id="acdfc-117">処理されている例外は、パラメーターによって参照されているスレッドオブジェクトから取得でき `pThread` ます。</span><span class="sxs-lookup"><span data-stu-id="acdfc-117">The exception being processed can be retrieved from the ICorDebugThread object referenced by the `pThread` parameter.</span></span>  
  
 <span data-ttu-id="acdfc-118">特定のフレームとオフセットは、パラメーターによって次のように決定され `dwEventType` ます。</span><span class="sxs-lookup"><span data-stu-id="acdfc-118">The particular frame and offset are determined by the `dwEventType` parameter as follows:</span></span>  
  
|<span data-ttu-id="acdfc-119">`dwEventType` の値</span><span class="sxs-lookup"><span data-stu-id="acdfc-119">Value of `dwEventType`</span></span>|<span data-ttu-id="acdfc-120">`pFrame` の値</span><span class="sxs-lookup"><span data-stu-id="acdfc-120">Value of `pFrame`</span></span>|<span data-ttu-id="acdfc-121">`nOffset` の値</span><span class="sxs-lookup"><span data-stu-id="acdfc-121">Value of `nOffset`</span></span>|  
|----------------------------|-----------------------|------------------------|  
|<span data-ttu-id="acdfc-122">DEBUG_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="acdfc-122">DEBUG_EXCEPTION_FIRST_CHANCE</span></span>|<span data-ttu-id="acdfc-123">例外をスローしたフレーム。</span><span class="sxs-lookup"><span data-stu-id="acdfc-123">The frame that threw the exception.</span></span>|<span data-ttu-id="acdfc-124">フレーム内の命令ポインター。</span><span class="sxs-lookup"><span data-stu-id="acdfc-124">The instruction pointer in the frame.</span></span>|  
|<span data-ttu-id="acdfc-125">DEBUG_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="acdfc-125">DEBUG_EXCEPTION_USER_FIRST_CHANCE</span></span>|<span data-ttu-id="acdfc-126">スローされた例外のポイントに最も近いユーザーコードフレーム。</span><span class="sxs-lookup"><span data-stu-id="acdfc-126">The user-code frame closest to the point of the thrown exception.</span></span>|<span data-ttu-id="acdfc-127">フレーム内の命令ポインター。</span><span class="sxs-lookup"><span data-stu-id="acdfc-127">The instruction pointer in the frame.</span></span>|  
|<span data-ttu-id="acdfc-128">DEBUG_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="acdfc-128">DEBUG_EXCEPTION_CATCH_HANDLER_FOUND</span></span>|<span data-ttu-id="acdfc-129">Catch ハンドラーを格納しているフレーム。</span><span class="sxs-lookup"><span data-stu-id="acdfc-129">The frame that contains the catch handler.</span></span>|<span data-ttu-id="acdfc-130">Catch ハンドラーの先頭の MSIL (Microsoft 中間言語) オフセット。</span><span class="sxs-lookup"><span data-stu-id="acdfc-130">The Microsoft intermediate language (MSIL) offset of the beginning of the catch handler.</span></span>|  
|<span data-ttu-id="acdfc-131">DEBUG_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="acdfc-131">DEBUG_EXCEPTION_UNHANDLED</span></span>|<span data-ttu-id="acdfc-132">NULL</span><span class="sxs-lookup"><span data-stu-id="acdfc-132">NULL</span></span>|<span data-ttu-id="acdfc-133">未定義です。</span><span class="sxs-lookup"><span data-stu-id="acdfc-133">Undefined.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="acdfc-134">必要条件</span><span class="sxs-lookup"><span data-stu-id="acdfc-134">Requirements</span></span>  
 <span data-ttu-id="acdfc-135">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="acdfc-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="acdfc-136">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="acdfc-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="acdfc-137">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="acdfc-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="acdfc-138">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="acdfc-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acdfc-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="acdfc-139">See also</span></span>

- [<span data-ttu-id="acdfc-140">ICorDebugManagedCallback2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="acdfc-140">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="acdfc-141">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="acdfc-141">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
