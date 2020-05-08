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
ms.openlocfilehash: a197d260c55d24f906da7d7f2768bb7ba1ad751f
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895347"
---
# <a name="icordebugsetmanagedhandler-method"></a><span data-ttu-id="d6e1a-102">ICorDebug::SetManagedHandler メソッド</span><span class="sxs-lookup"><span data-stu-id="d6e1a-102">ICorDebug::SetManagedHandler Method</span></span>
<span data-ttu-id="d6e1a-103">マネージイベントのイベントハンドラーオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="d6e1a-103">Specifies the event handler object for managed events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6e1a-104">構文</span><span class="sxs-lookup"><span data-stu-id="d6e1a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetManagedHandler (  
    [in] ICorDebugManagedCallback     *pCallback  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d6e1a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d6e1a-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="d6e1a-106">からイベントハンドラーオブジェクトである、ツール[コールバック](icordebugmanagedcallback-interface.md)オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d6e1a-106">[in] A pointer to an [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) object, which is the event handler object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6e1a-107">解説</span><span class="sxs-lookup"><span data-stu-id="d6e1a-107">Remarks</span></span>  
 <span data-ttu-id="d6e1a-108">`SetManagedHandler`作成時にを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6e1a-108">`SetManagedHandler` must be called at creation time.</span></span>  
  
 <span data-ttu-id="d6e1a-109">の`ICorDebugManagedCallback`実装に、デバッグ対象のアプリケーションのデバッグイベントを処理するための十分なインターフェイスが`SetManagedHandler`含まれていない場合は、E_NOINTERFACE の HRESULT が返されます。</span><span class="sxs-lookup"><span data-stu-id="d6e1a-109">If the `ICorDebugManagedCallback` implementation does not contain sufficient interfaces to handle debugging events for the application that is being debugged, `SetManagedHandler` returns an HRESULT of E_NOINTERFACE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6e1a-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="d6e1a-110">Requirements</span></span>  
 <span data-ttu-id="d6e1a-111">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6e1a-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6e1a-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d6e1a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d6e1a-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d6e1a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6e1a-114">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6e1a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6e1a-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="d6e1a-115">See also</span></span>

- [<span data-ttu-id="d6e1a-116">ICorDebug インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d6e1a-116">ICorDebug Interface</span></span>](icordebug-interface.md)
