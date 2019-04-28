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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4b1c85499e5269027da2c2a01ab67aab2c5da626
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775551"
---
# <a name="icordebugprocessmodifylogswitch-method"></a><span data-ttu-id="159a3-102">ICorDebugProcess::ModifyLogSwitch メソッド</span><span class="sxs-lookup"><span data-stu-id="159a3-102">ICorDebugProcess::ModifyLogSwitch Method</span></span>
<span data-ttu-id="159a3-103">指定したログ スイッチの重大度レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="159a3-103">Sets the severity level of the specified log switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="159a3-104">構文</span><span class="sxs-lookup"><span data-stu-id="159a3-104">Syntax</span></span>  
  
```  
HRESULT ModifyLogSwitch(  
    [in] WCHAR *pLogSwitchName,  
    [in] LONG  lLevel);  
```  
  
## <a name="parameters"></a><span data-ttu-id="159a3-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="159a3-105">Parameters</span></span>  
 `pLogSwitchName`  
 <span data-ttu-id="159a3-106">[in]Log スイッチの名前を指定する文字列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="159a3-106">[in] A pointer to a string that specifies the name of the log switch.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="159a3-107">[in]指定したログ スイッチを設定する重大度レベル。</span><span class="sxs-lookup"><span data-stu-id="159a3-107">[in] The severity level to be set for the specified log switch.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="159a3-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="159a3-108">Remarks</span></span>  
 <span data-ttu-id="159a3-109">このメソッドが後でのみ有効では、 [icordebugmanagedcallback::createprocess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md)コールバックが発生しました。</span><span class="sxs-lookup"><span data-stu-id="159a3-109">This method is valid only after the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="159a3-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="159a3-110">Requirements</span></span>  
 <span data-ttu-id="159a3-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="159a3-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="159a3-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="159a3-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="159a3-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="159a3-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="159a3-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="159a3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
