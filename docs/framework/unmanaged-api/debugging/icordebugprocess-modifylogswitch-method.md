---
title: ICorDebugProcess::ModifyLogSwitch メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ModifyLogSwitch
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ModifyLogSwitch
helpviewer_keywords:
- ICorDebugProcess::ModifyLogSwitch method [.NET Framework debugging]
- ModifyLogSwitch method [.NET Framework debugging]
ms.assetid: 5fd30875-555e-4e96-877b-5dd266cde7c4
topic_type:
- apiref
ms.openlocfilehash: 86b8737577bdb5f61f1061cb217620fae03ebd0c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139376"
---
# <a name="icordebugprocessmodifylogswitch-method"></a><span data-ttu-id="66aba-102">ICorDebugProcess::ModifyLogSwitch メソッド</span><span class="sxs-lookup"><span data-stu-id="66aba-102">ICorDebugProcess::ModifyLogSwitch Method</span></span>
<span data-ttu-id="66aba-103">指定されたログスイッチの重大度レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="66aba-103">Sets the severity level of the specified log switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66aba-104">構文</span><span class="sxs-lookup"><span data-stu-id="66aba-104">Syntax</span></span>  
  
```cpp  
HRESULT ModifyLogSwitch(  
    [in] WCHAR *pLogSwitchName,  
    [in] LONG  lLevel);  
```  
  
## <a name="parameters"></a><span data-ttu-id="66aba-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="66aba-105">Parameters</span></span>  
 `pLogSwitchName`  
 <span data-ttu-id="66aba-106">からログスイッチの名前を指定する文字列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="66aba-106">[in] A pointer to a string that specifies the name of the log switch.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="66aba-107">から指定されたログスイッチに設定される重大度レベル。</span><span class="sxs-lookup"><span data-stu-id="66aba-107">[in] The severity level to be set for the specified log switch.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="66aba-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="66aba-108">Remarks</span></span>  
 <span data-ttu-id="66aba-109">このメソッドは、によって実行される場合にのみ有効です: [: CreateProcess managedcallback:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md)コールバックが発生しました。</span><span class="sxs-lookup"><span data-stu-id="66aba-109">This method is valid only after the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66aba-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="66aba-110">Requirements</span></span>  
 <span data-ttu-id="66aba-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66aba-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66aba-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="66aba-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="66aba-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="66aba-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="66aba-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66aba-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
