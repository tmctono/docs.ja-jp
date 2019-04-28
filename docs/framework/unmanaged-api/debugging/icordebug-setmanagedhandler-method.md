---
title: ICorDebug::SetManagedHandler メソッド
ms.date: 03/30/2017
api_name:
- ICorDebug.SetManagedHandler
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::SetManagedHandler
helpviewer_keywords:
- ICorDebug::SetManagedHandler method [.NET Framework debugging]
- SetManagedHandler method [.NET Framework debugging]
ms.assetid: d079131b-685b-4869-95be-826b88d28bd2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 88f30089879f2d023c8fb04b52e75b2942da2a83
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61786348"
---
# <a name="icordebugsetmanagedhandler-method"></a><span data-ttu-id="b7997-102">ICorDebug::SetManagedHandler メソッド</span><span class="sxs-lookup"><span data-stu-id="b7997-102">ICorDebug::SetManagedHandler Method</span></span>
<span data-ttu-id="b7997-103">管理対象のイベントのイベント ハンドラー オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="b7997-103">Specifies the event handler object for managed events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7997-104">構文</span><span class="sxs-lookup"><span data-stu-id="b7997-104">Syntax</span></span>  
  
```  
HRESULT SetManagedHandler (  
    [in] ICorDebugManagedCallback     *pCallback  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b7997-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b7997-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="b7997-106">[in]ポインター、 [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)イベント ハンドラー オブジェクトであるオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="b7997-106">[in] A pointer to an [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) object, which is the event handler object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b7997-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="b7997-107">Remarks</span></span>  
 <span data-ttu-id="b7997-108">`SetManagedHandler` 作成時に呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7997-108">`SetManagedHandler` must be called at creation time.</span></span>  
  
 <span data-ttu-id="b7997-109">場合、`ICorDebugManagedCallback`実装には、デバッグ中、アプリケーションのデバッグ イベントを処理するための十分なインターフェイスが含まれていない`SetManagedHandler`HRESULT の E_NOINTERFACE を返します。</span><span class="sxs-lookup"><span data-stu-id="b7997-109">If the `ICorDebugManagedCallback` implementation does not contain sufficient interfaces to handle debugging events for the application that is being debugged, `SetManagedHandler` returns an HRESULT of E_NOINTERFACE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7997-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="b7997-110">Requirements</span></span>  
 <span data-ttu-id="b7997-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7997-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7997-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b7997-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b7997-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7997-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7997-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7997-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7997-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="b7997-115">See also</span></span>

- [<span data-ttu-id="b7997-116">ICorDebug インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b7997-116">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
