---
title: ICorDebugManagedCallback::LogMessage メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LogMessage
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LogMessage
helpviewer_keywords:
- ICorDebugManagedCallback::LogMessage method [.NET Framework debugging]
- LogMessage method [.NET Framework debugging]
ms.assetid: d218554a-bf42-4d88-833d-ede30de67a53
topic_type:
- apiref
ms.openlocfilehash: d95662167dbc8fcda049fb6a7b3e6ff1dfb6e736
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130705"
---
# <a name="icordebugmanagedcallbacklogmessage-method"></a><span data-ttu-id="d9ea8-102">ICorDebugManagedCallback::LogMessage メソッド</span><span class="sxs-lookup"><span data-stu-id="d9ea8-102">ICorDebugManagedCallback::LogMessage Method</span></span>
<span data-ttu-id="d9ea8-103">共通言語ランタイム (CLR) マネージスレッドが、イベントを記録するために <xref:System.Diagnostics.EventLog> クラスのメソッドを呼び出したことをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="d9ea8-103">Notifies the debugger that a common language runtime (CLR) managed thread has called a method in the <xref:System.Diagnostics.EventLog> class to log an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9ea8-104">構文</span><span class="sxs-lookup"><span data-stu-id="d9ea8-104">Syntax</span></span>  
  
```cpp  
HRESULT LogMessage (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pMessage  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9ea8-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d9ea8-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="d9ea8-106">からイベントを記録したマネージスレッドを含むアプリケーションドメインを表す、コードのオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d9ea8-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread that logged the event.</span></span>  
  
 `pThread`  
 <span data-ttu-id="d9ea8-107">からマネージスレッドを表す、コードスレッドオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d9ea8-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="d9ea8-108">からイベントログに書き込まれた説明メッセージの重大度レベルを示す、ログ記録[Levelenum](../../../../docs/framework/unmanaged-api/debugging/logginglevelenum-enumeration.md)列挙体の値。</span><span class="sxs-lookup"><span data-stu-id="d9ea8-108">[in] A value of the [LoggingLevelEnum](../../../../docs/framework/unmanaged-api/debugging/logginglevelenum-enumeration.md) enumeration that indicates the severity level of the descriptive message that was written to the event log.</span></span>  
  
 `pLogSwitchName`  
 <span data-ttu-id="d9ea8-109">からトレーススイッチの名前へのポインター。</span><span class="sxs-lookup"><span data-stu-id="d9ea8-109">[in] A pointer to the name of the tracing switch.</span></span>  
  
 `pMessage`  
 <span data-ttu-id="d9ea8-110">からイベントログに書き込まれたメッセージへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d9ea8-110">[in] A pointer to the message that was written to the event log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9ea8-111">［要件］</span><span class="sxs-lookup"><span data-stu-id="d9ea8-111">Requirements</span></span>  
 <span data-ttu-id="d9ea8-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9ea8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9ea8-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d9ea8-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d9ea8-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d9ea8-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d9ea8-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9ea8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9ea8-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="d9ea8-116">See also</span></span>

- [<span data-ttu-id="d9ea8-117">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d9ea8-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
