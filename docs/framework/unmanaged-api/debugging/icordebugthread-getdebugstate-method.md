---
title: ICorDebugThread::GetDebugState メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetDebugState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetDebugState
helpviewer_keywords:
- GetDebugState method [.NET Framework debugging]
- ICorDebugThread::GetDebugState method [.NET Framework debugging]
ms.assetid: 9be27b0c-1d99-4722-b0d4-40cf6753ce5c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 68df19120f2e0b45e73f9d5e137afc8a5e7ac513
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489892"
---
# <a name="icordebugthreadgetdebugstate-method"></a><span data-ttu-id="c8b40-102">ICorDebugThread::GetDebugState メソッド</span><span class="sxs-lookup"><span data-stu-id="c8b40-102">ICorDebugThread::GetDebugState Method</span></span>
<span data-ttu-id="c8b40-103">この ICorDebugThread オブジェクトの現在のデバッグ状態を取得します。</span><span class="sxs-lookup"><span data-stu-id="c8b40-103">Gets the current debug state of this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8b40-104">構文</span><span class="sxs-lookup"><span data-stu-id="c8b40-104">Syntax</span></span>  
  
```  
HRESULT GetDebugState (  
    [out] CorDebugThreadState   *pState  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c8b40-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c8b40-105">Parameters</span></span>  
 `pState`  
 <span data-ttu-id="c8b40-106">[out]このスレッドの現在のデバッグ状態を説明する CorDebugThreadState 列挙値のビットごとの組み合わせへのポインター。</span><span class="sxs-lookup"><span data-stu-id="c8b40-106">[out] A pointer to a bitwise combination of CorDebugThreadState enumeration values that describes the current debug state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c8b40-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="c8b40-107">Remarks</span></span>  
 <span data-ttu-id="c8b40-108">プロセスが現在停止している場合`pState`プロセスに続く、このスレッドの実際の現在状態にない場合は、このスレッドの存在のデバッグ状態を表します。</span><span class="sxs-lookup"><span data-stu-id="c8b40-108">If the process is currently stopped, `pState` represents the debug state that would exist for this thread if the process were to be continued, not the actual current state of this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8b40-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="c8b40-109">Requirements</span></span>  
 <span data-ttu-id="c8b40-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8b40-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8b40-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c8b40-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c8b40-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c8b40-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c8b40-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8b40-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
