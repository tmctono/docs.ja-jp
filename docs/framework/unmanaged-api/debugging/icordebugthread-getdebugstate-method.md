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
ms.openlocfilehash: 13125f60f596cb8a80d9c42c51a979f632de494b
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379754"
---
# <a name="icordebugthreadgetdebugstate-method"></a><span data-ttu-id="2101f-102">ICorDebugThread::GetDebugState メソッド</span><span class="sxs-lookup"><span data-stu-id="2101f-102">ICorDebugThread::GetDebugState Method</span></span>
<span data-ttu-id="2101f-103">このスレッドオブジェクトの現在のデバッグ状態を取得します。</span><span class="sxs-lookup"><span data-stu-id="2101f-103">Gets the current debug state of this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2101f-104">構文</span><span class="sxs-lookup"><span data-stu-id="2101f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDebugState (  
    [out] CorDebugThreadState   *pState  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2101f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2101f-105">Parameters</span></span>  
 `pState`  
 <span data-ttu-id="2101f-106">入出力このスレッドの現在のデバッグ状態を示す CorDebugThreadState 列挙値のビットごとの組み合わせへのポインター。</span><span class="sxs-lookup"><span data-stu-id="2101f-106">[out] A pointer to a bitwise combination of CorDebugThreadState enumeration values that describes the current debug state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2101f-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="2101f-107">Remarks</span></span>  
 <span data-ttu-id="2101f-108">プロセスが現在停止されている場合、は、 `pState` このスレッドの実際の現在の状態ではなく、プロセスが続行された場合に存在する可能性があるデバッグ状態を表します。</span><span class="sxs-lookup"><span data-stu-id="2101f-108">If the process is currently stopped, `pState` represents the debug state that would exist for this thread if the process were to be continued, not the actual current state of this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2101f-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="2101f-109">Requirements</span></span>  
 <span data-ttu-id="2101f-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2101f-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2101f-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2101f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2101f-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2101f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2101f-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2101f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
