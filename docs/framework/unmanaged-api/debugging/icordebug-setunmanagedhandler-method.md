---
title: ICorDebug::SetUnmanagedHandler メソッド
ms.date: 03/30/2017
api_name:
- ICorDebug.SetUnmanagedHandler
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::SetUnmanagerHandler
helpviewer_keywords:
- SetUnmanagedHandler method [.NET Framework debugging]
- ICorDebug::SetUnmanagedHandler method [.NET Framework debugging]
ms.assetid: 6b546be4-f86d-4536-8cfc-1d08e5066eb6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 49567bc354ddad56311268bef0a367b8896f2ab8
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57475672"
---
# <a name="icordebugsetunmanagedhandler-method"></a><span data-ttu-id="398db-102">ICorDebug::SetUnmanagedHandler メソッド</span><span class="sxs-lookup"><span data-stu-id="398db-102">ICorDebug::SetUnmanagedHandler Method</span></span>
<span data-ttu-id="398db-103">非管理対象のイベントのイベント ハンドラー オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="398db-103">Specifies the event handler object for unmanaged events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="398db-104">構文</span><span class="sxs-lookup"><span data-stu-id="398db-104">Syntax</span></span>  
  
```  
HRESULT SetUnmanagedHandler (  
    [in] ICorDebugUnmanagedCallback  *pCallback  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="398db-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="398db-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="398db-106">[in]ポインター、 [ICorDebugUnmanagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md)非管理対象のイベントのイベント ハンドラーを表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="398db-106">[in] A pointer to an [ICorDebugUnmanagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md) object that represents the event handler for unmanaged events.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="398db-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="398db-107">Remarks</span></span>  
 <span data-ttu-id="398db-108">イベント ハンドラー オブジェクトのアンマネージ呼び出しの後にイベントを設定する必要があります[icordebug::initialize](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md)と呼び出しの前に[icordebug::createprocess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md)または[icordebug::debugactiveprocess](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md).</span><span class="sxs-lookup"><span data-stu-id="398db-108">The event handler object for unmanaged events must be set after a call to [ICorDebug::Initialize](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md) and before any calls to [ICorDebug::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) or [ICorDebug::DebugActiveProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md).</span></span> <span data-ttu-id="398db-109">ただし、レガシー目的のための必要はありません、最初のネイティブ デバッグ イベントが発生するまでの非管理対象のイベントのイベントのハンドラー オブジェクトを設定します。</span><span class="sxs-lookup"><span data-stu-id="398db-109">However, for legacy purposes, you are not required to set the event handler object for unmanaged events until the first native debug event is raised.</span></span> <span data-ttu-id="398db-110">具体的には場合、`ICorDebug::CreateProcess`ネイティブ デバッグのメイン スレッドが再開されるまで、イベントをディスパッチすることはできません、CREATE_SUSPENDED フラグが設定されます。</span><span class="sxs-lookup"><span data-stu-id="398db-110">Specifically, if `ICorDebug::CreateProcess` has set the CREATE_SUSPENDED flag, native debug events cannot be dispatched until the main thread is resumed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="398db-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="398db-111">Requirements</span></span>  
 <span data-ttu-id="398db-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="398db-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="398db-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="398db-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="398db-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="398db-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="398db-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="398db-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="398db-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="398db-116">See also</span></span>
- [<span data-ttu-id="398db-117">ICorDebug インターフェイス</span><span class="sxs-lookup"><span data-stu-id="398db-117">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
