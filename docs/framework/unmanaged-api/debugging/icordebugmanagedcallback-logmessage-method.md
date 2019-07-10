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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 14b10b94f66a6b5434befeac1cd9562cb8a0f27f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67761559"
---
# <a name="icordebugmanagedcallbacklogmessage-method"></a><span data-ttu-id="3911c-102">ICorDebugManagedCallback::LogMessage メソッド</span><span class="sxs-lookup"><span data-stu-id="3911c-102">ICorDebugManagedCallback::LogMessage Method</span></span>
<span data-ttu-id="3911c-103">共通言語ランタイム (CLR) によって管理されるスレッドがメソッドを呼び出すことをデバッガーに通知、<xref:System.Diagnostics.EventLog>クラスをイベント ログに記録します。</span><span class="sxs-lookup"><span data-stu-id="3911c-103">Notifies the debugger that a common language runtime (CLR) managed thread has called a method in the <xref:System.Diagnostics.EventLog> class to log an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3911c-104">構文</span><span class="sxs-lookup"><span data-stu-id="3911c-104">Syntax</span></span>  
  
```cpp  
HRESULT LogMessage (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pMessage  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3911c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3911c-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="3911c-106">[in]イベントを記録したマネージ スレッドを格納しているアプリケーション ドメインを表す ICorDebugAppDomain オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="3911c-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread that logged the event.</span></span>  
  
 `pThread`  
 <span data-ttu-id="3911c-107">[in]マネージ スレッドを表す ICorDebugThread オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="3911c-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="3911c-108">[in]値、 [LoggingLevelEnum](../../../../docs/framework/unmanaged-api/debugging/logginglevelenum-enumeration.md)イベント ログに書き込まれた内容を示すメッセージの重大度レベルを示す列挙体。</span><span class="sxs-lookup"><span data-stu-id="3911c-108">[in] A value of the [LoggingLevelEnum](../../../../docs/framework/unmanaged-api/debugging/logginglevelenum-enumeration.md) enumeration that indicates the severity level of the descriptive message that was written to the event log.</span></span>  
  
 `pLogSwitchName`  
 <span data-ttu-id="3911c-109">[in]トレース スイッチの名前へのポインター。</span><span class="sxs-lookup"><span data-stu-id="3911c-109">[in] A pointer to the name of the tracing switch.</span></span>  
  
 `pMessage`  
 <span data-ttu-id="3911c-110">[in]イベント ログに書き込まれたメッセージへのポインター。</span><span class="sxs-lookup"><span data-stu-id="3911c-110">[in] A pointer to the message that was written to the event log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3911c-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="3911c-111">Requirements</span></span>  
 <span data-ttu-id="3911c-112">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3911c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3911c-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3911c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3911c-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3911c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3911c-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3911c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3911c-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="3911c-116">See also</span></span>

- [<span data-ttu-id="3911c-117">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3911c-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
