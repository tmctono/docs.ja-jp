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
ms.openlocfilehash: c60af0ccfb143e68be3b987b0caf92fe3d992b4d
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212712"
---
# <a name="icordebugmanagedcallbacklogmessage-method"></a><span data-ttu-id="f1adf-102">ICorDebugManagedCallback::LogMessage メソッド</span><span class="sxs-lookup"><span data-stu-id="f1adf-102">ICorDebugManagedCallback::LogMessage Method</span></span>
<span data-ttu-id="f1adf-103">共通言語ランタイム (CLR) マネージスレッドが、 <xref:System.Diagnostics.EventLog> イベントを記録するためにクラスのメソッドを呼び出したことをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="f1adf-103">Notifies the debugger that a common language runtime (CLR) managed thread has called a method in the <xref:System.Diagnostics.EventLog> class to log an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1adf-104">構文</span><span class="sxs-lookup"><span data-stu-id="f1adf-104">Syntax</span></span>  
  
```cpp  
HRESULT LogMessage (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pMessage  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1adf-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f1adf-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="f1adf-106">からイベントを記録したマネージスレッドを含むアプリケーションドメインを表す、コードのオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="f1adf-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread that logged the event.</span></span>  
  
 `pThread`  
 <span data-ttu-id="f1adf-107">からマネージスレッドを表す、コードスレッドオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="f1adf-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="f1adf-108">からイベントログに書き込まれた説明メッセージの重大度レベルを示す、ログ記録[Levelenum](logginglevelenum-enumeration.md)列挙体の値。</span><span class="sxs-lookup"><span data-stu-id="f1adf-108">[in] A value of the [LoggingLevelEnum](logginglevelenum-enumeration.md) enumeration that indicates the severity level of the descriptive message that was written to the event log.</span></span>  
  
 `pLogSwitchName`  
 <span data-ttu-id="f1adf-109">からトレーススイッチの名前へのポインター。</span><span class="sxs-lookup"><span data-stu-id="f1adf-109">[in] A pointer to the name of the tracing switch.</span></span>  
  
 `pMessage`  
 <span data-ttu-id="f1adf-110">からイベントログに書き込まれたメッセージへのポインター。</span><span class="sxs-lookup"><span data-stu-id="f1adf-110">[in] A pointer to the message that was written to the event log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1adf-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="f1adf-111">Requirements</span></span>  
 <span data-ttu-id="f1adf-112">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1adf-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1adf-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f1adf-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f1adf-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1adf-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1adf-115">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1adf-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1adf-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="f1adf-116">See also</span></span>

- [<span data-ttu-id="f1adf-117">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f1adf-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
