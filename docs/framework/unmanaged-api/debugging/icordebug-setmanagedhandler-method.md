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
ms.openlocfilehash: 88a007654646ba42ebcaf1b42e002282a1040c7f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134064"
---
# <a name="icordebugsetmanagedhandler-method"></a><span data-ttu-id="23383-102">ICorDebug::SetManagedHandler メソッド</span><span class="sxs-lookup"><span data-stu-id="23383-102">ICorDebug::SetManagedHandler Method</span></span>
<span data-ttu-id="23383-103">マネージイベントのイベントハンドラーオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="23383-103">Specifies the event handler object for managed events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23383-104">構文</span><span class="sxs-lookup"><span data-stu-id="23383-104">Syntax</span></span>  
  
```cpp  
HRESULT SetManagedHandler (  
    [in] ICorDebugManagedCallback     *pCallback  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="23383-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="23383-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="23383-106">からイベントハンドラーオブジェクトである、ツール[コールバック](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="23383-106">[in] A pointer to an [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) object, which is the event handler object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="23383-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="23383-107">Remarks</span></span>  
 <span data-ttu-id="23383-108">`SetManagedHandler` は、作成時に呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="23383-108">`SetManagedHandler` must be called at creation time.</span></span>  
  
 <span data-ttu-id="23383-109">`ICorDebugManagedCallback` の実装に、デバッグ中のアプリケーションのデバッグイベントを処理するための十分なインターフェイスが含まれていない場合、`SetManagedHandler` は E_NOINTERFACE の HRESULT を返します。</span><span class="sxs-lookup"><span data-stu-id="23383-109">If the `ICorDebugManagedCallback` implementation does not contain sufficient interfaces to handle debugging events for the application that is being debugged, `SetManagedHandler` returns an HRESULT of E_NOINTERFACE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23383-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="23383-110">Requirements</span></span>  
 <span data-ttu-id="23383-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23383-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23383-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="23383-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="23383-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="23383-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="23383-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23383-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23383-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="23383-115">See also</span></span>

- [<span data-ttu-id="23383-116">ICorDebug インターフェイス</span><span class="sxs-lookup"><span data-stu-id="23383-116">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
