---
title: ICorDebugManagedCallback::LogSwitch メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LogSwitch
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LogSwitch
helpviewer_keywords:
- LogSwitch method [.NET Framework debugging]
- ICorDebugManagedCallback::LogSwitch method [.NET Framework debugging]
ms.assetid: 0ac59d27-783f-4a87-b7a8-baa3ccc54582
topic_type:
- apiref
ms.openlocfilehash: a72eabb1b405c67f5603164e56a589a237603d2f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130691"
---
# <a name="icordebugmanagedcallbacklogswitch-method"></a><span data-ttu-id="9e7c5-102">ICorDebugManagedCallback::LogSwitch メソッド</span><span class="sxs-lookup"><span data-stu-id="9e7c5-102">ICorDebugManagedCallback::LogSwitch Method</span></span>
<span data-ttu-id="9e7c5-103">共通言語ランタイム (CLR) マネージスレッドが、デバッグ/トレーススイッチを作成、変更、または削除するために <xref:System.Diagnostics.Switch> クラスのメソッドを呼び出したことをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="9e7c5-103">Notifies the debugger that a common language runtime (CLR) managed thread has called a method in the <xref:System.Diagnostics.Switch> class to create, modify, or delete a debugging/tracing switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e7c5-104">構文</span><span class="sxs-lookup"><span data-stu-id="9e7c5-104">Syntax</span></span>  
  
```cpp  
HRESULT LogSwitch (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] ULONG                ulReason,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pParentName);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e7c5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9e7c5-105">Parameters</span></span>  
 `PAppDomain`  
 <span data-ttu-id="9e7c5-106">からデバッグ/トレーススイッチを作成、変更、または削除したマネージスレッドを含むアプリケーションドメインを表す、コードのオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="9e7c5-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread that created, modified, or deleted a debugging/tracing switch.</span></span>  
  
 `pThread`  
 <span data-ttu-id="9e7c5-107">からマネージスレッドを表す、コードスレッドオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="9e7c5-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="9e7c5-108">からイベントログに書き込まれた説明メッセージの重大度レベルを示す値。</span><span class="sxs-lookup"><span data-stu-id="9e7c5-108">[in] A value that indicates the severity level of the descriptive message that was written to the event log.</span></span>  
  
 `ulReason`  
 <span data-ttu-id="9e7c5-109">からデバッグ/トレーススイッチで実行された操作を示す[Logswitchcallreason](../../../../docs/framework/unmanaged-api/debugging/logswitchcallreason-enumeration.md)列挙体の値。</span><span class="sxs-lookup"><span data-stu-id="9e7c5-109">[in] A value of the [LogSwitchCallReason](../../../../docs/framework/unmanaged-api/debugging/logswitchcallreason-enumeration.md) enumeration that indicates the operation performed on the debugging/tracing switch.</span></span>  
  
 `pLogSwitchName`  
 <span data-ttu-id="9e7c5-110">からデバッグ/トレーススイッチの名前へのポインター。</span><span class="sxs-lookup"><span data-stu-id="9e7c5-110">[in] A pointer to the name of the debugging/tracing switch.</span></span>  
  
 `pParentName`  
 <span data-ttu-id="9e7c5-111">からデバッグ/トレーススイッチの親の名前へのポインター。</span><span class="sxs-lookup"><span data-stu-id="9e7c5-111">[in] A pointer to the name of the parent of the debugging/tracing switch.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e7c5-112">［要件］</span><span class="sxs-lookup"><span data-stu-id="9e7c5-112">Requirements</span></span>  
 <span data-ttu-id="9e7c5-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e7c5-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e7c5-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9e7c5-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9e7c5-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9e7c5-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9e7c5-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e7c5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e7c5-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="9e7c5-117">See also</span></span>

- [<span data-ttu-id="9e7c5-118">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9e7c5-118">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
