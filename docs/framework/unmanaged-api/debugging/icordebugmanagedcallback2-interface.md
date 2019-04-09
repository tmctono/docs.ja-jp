---
title: ICorDebugManagedCallback2 インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2
helpviewer_keywords:
- ICorDebugManagedCallback2 interface [.NET Framework debugging]
ms.assetid: cf7b7cfa-1c4b-4d8c-be70-4f9ed15a788b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f1ecfea208f87f53f15fcc4cdafb58341c293e43
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59096089"
---
# <a name="icordebugmanagedcallback2-interface"></a><span data-ttu-id="fe391-102">ICorDebugManagedCallback2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fe391-102">ICorDebugManagedCallback2 Interface</span></span>
<span data-ttu-id="fe391-103">デバッガーの例外処理およびマネージド デバッグ アシスタント (MDA: Managed Debugging Assistants) をサポートするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="fe391-103">Provides methods to support debugger exception handling and managed debugging assistants (MDAs).</span></span> `ICorDebugManagedCallback2` <span data-ttu-id="fe391-104">論理拡張機能は、 [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="fe391-104">is a logical extension of the [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fe391-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="fe391-105">Methods</span></span>  
  
|<span data-ttu-id="fe391-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="fe391-106">Method</span></span>|<span data-ttu-id="fe391-107">説明</span><span class="sxs-lookup"><span data-stu-id="fe391-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fe391-108">ChangeConnection メソッド</span><span class="sxs-lookup"><span data-stu-id="fe391-108">ChangeConnection Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-changeconnection-method.md)|<span data-ttu-id="fe391-109">指定された接続に関連付けられているタスクのセットが変更されたことをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="fe391-109">Notifies the debugger that the set of tasks associated with the specified connection has changed.</span></span>|  
|[<span data-ttu-id="fe391-110">CreateConnection メソッド</span><span class="sxs-lookup"><span data-stu-id="fe391-110">CreateConnection Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-createconnection-method.md)|<span data-ttu-id="fe391-111">新しい接続が作成されたことをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="fe391-111">Notifies the debugger that a new connection has been created.</span></span>|  
|[<span data-ttu-id="fe391-112">DestroyConnection メソッド</span><span class="sxs-lookup"><span data-stu-id="fe391-112">DestroyConnection Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-destroyconnection-method.md)|<span data-ttu-id="fe391-113">指定した接続が終了されたことをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="fe391-113">Notifies the debugger that the specified connection has been terminated.</span></span>|  
|[<span data-ttu-id="fe391-114">Exception メソッド</span><span class="sxs-lookup"><span data-stu-id="fe391-114">Exception Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md)|<span data-ttu-id="fe391-115">例外ハンドラーの検索が開始されたことをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="fe391-115">Notifies the debugger that a search for an exception handler has started.</span></span>|  
|[<span data-ttu-id="fe391-116">ExceptionUnwind メソッド</span><span class="sxs-lookup"><span data-stu-id="fe391-116">ExceptionUnwind Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exceptionunwind-method.md)|<span data-ttu-id="fe391-117">例外のアンワインド処理中に状態の通知を提供します。</span><span class="sxs-lookup"><span data-stu-id="fe391-117">Provides a status notification during the exception unwinding process.</span></span>|  
|[<span data-ttu-id="fe391-118">FunctionRemapComplete メソッド</span><span class="sxs-lookup"><span data-stu-id="fe391-118">FunctionRemapComplete Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapcomplete-method.md)|<span data-ttu-id="fe391-119">編集された関数の新しいバージョンにコードが実行を切り替えたことをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="fe391-119">Notifies the debugger that code execution has switched to a new version of an edited function.</span></span>|  
|[<span data-ttu-id="fe391-120">FunctionRemapOpportunity メソッド</span><span class="sxs-lookup"><span data-stu-id="fe391-120">FunctionRemapOpportunity Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapopportunity-method.md)|<span data-ttu-id="fe391-121">コードの実行が編集された関数の以前のバージョンでシーケンス ポイントに達したことをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="fe391-121">Notifies the debugger that code execution has reached a sequence point in an older version of an edited function.</span></span>|  
|[<span data-ttu-id="fe391-122">MDANotification メソッド</span><span class="sxs-lookup"><span data-stu-id="fe391-122">MDANotification Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-mdanotification-method.md)|<span data-ttu-id="fe391-123">コードの実行がマネージ デバッグ アシスタント (MDA) メッセージを発生したことの通知を提供します。</span><span class="sxs-lookup"><span data-stu-id="fe391-123">Provides notification that code execution has encountered a managed debugging assistant (MDA) message.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fe391-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="fe391-124">Remarks</span></span>  
 <span data-ttu-id="fe391-125">`ICorDebugManagedCallback2`インターフェイスは、拡張、 `ICorDebugManagedCallback` .NET Framework version 2.0 で導入された新しいデバッグ イベントを処理するインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="fe391-125">The `ICorDebugManagedCallback2` interface extends the `ICorDebugManagedCallback` interface to handle new debug events introduced in the .NET Framework version 2.0.</span></span>  
  
 <span data-ttu-id="fe391-126">デバッガーを実装する必要があります`ICorDebugManagedCallback2`場合は、.NET Framework 2.0 アプリケーションのデバッグします。</span><span class="sxs-lookup"><span data-stu-id="fe391-126">A debugger must implement `ICorDebugManagedCallback2` if it is debugging .NET Framework 2.0 applications.</span></span> <span data-ttu-id="fe391-127">インスタンス`ICorDebugManagedCallback`または`ICorDebugManagedCallback2`をコールバック オブジェクトとして渡される[icordebug::setmanagedhandler](../../../../docs/framework/unmanaged-api/debugging/icordebug-setmanagedhandler-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="fe391-127">An instance of `ICorDebugManagedCallback` or `ICorDebugManagedCallback2` is passed as the callback object to [ICorDebug::SetManagedHandler](../../../../docs/framework/unmanaged-api/debugging/icordebug-setmanagedhandler-method.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fe391-128">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="fe391-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe391-129">必要条件</span><span class="sxs-lookup"><span data-stu-id="fe391-129">Requirements</span></span>  
 <span data-ttu-id="fe391-130">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe391-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe391-131">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fe391-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fe391-132">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fe391-132">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="fe391-133">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="fe391-133">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fe391-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="fe391-134">See also</span></span>

- [<span data-ttu-id="fe391-135">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="fe391-135">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="fe391-136">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="fe391-136">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="fe391-137">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fe391-137">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
