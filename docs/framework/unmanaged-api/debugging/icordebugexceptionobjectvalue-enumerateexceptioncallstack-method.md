---
title: ICorDebugExceptionObjectValue::EnumerateExceptionCallStack メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectValue.EnumerateExceptionCallStack
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectValue::EnumerateExceptionCallStack
helpviewer_keywords:
- EnumerateExceptionCallStack method, ICorDebugExceptionObjectValue interface [.NET Framework debugging]
- ICorDebugExceptionObjectValue::EnumerateExceptionCallStack method [.NET Framework debugging]
ms.assetid: 00c64533-15dd-47f4-bb97-fe80a1ebadef
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9a58a62dbcd69d1847ab5a0b0109fe4eea53a4f3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754229"
---
# <a name="icordebugexceptionobjectvalueenumerateexceptioncallstack-method"></a><span data-ttu-id="1d043-102">ICorDebugExceptionObjectValue::EnumerateExceptionCallStack メソッド</span><span class="sxs-lookup"><span data-stu-id="1d043-102">ICorDebugExceptionObjectValue::EnumerateExceptionCallStack Method</span></span>
<span data-ttu-id="1d043-103">呼び出し履歴を例外オブジェクトに埋め込まれている列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="1d043-103">Gets an enumerator to the call stack embedded in an exception object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d043-104">構文</span><span class="sxs-lookup"><span data-stu-id="1d043-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateExceptionCallStack(  
    [out] ICorDebugExceptionObjectCallStackEnum **ppCallStackEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1d043-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1d043-105">Parameters</span></span>  
 <span data-ttu-id="1d043-106">ppCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="1d043-106">ppCallStackEnum</span></span>  
 <span data-ttu-id="1d043-107">[out]アドレスへのポインター、 [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)インターフェイス オブジェクトはマネージ例外オブジェクトのスタック トレースの列挙子です。</span><span class="sxs-lookup"><span data-stu-id="1d043-107">[out] A pointer to the address of an [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) interface object that is a stack trace enumerator for a managed exception object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1d043-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="1d043-108">Remarks</span></span>  
 <span data-ttu-id="1d043-109">呼び出し履歴情報がないかどうか、メソッドを返します`S_OK`、および[ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)は長さ 0 の有効な列挙子です。</span><span class="sxs-lookup"><span data-stu-id="1d043-109">If no call stack information is available, the method returns `S_OK`, and [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) is a valid enumerator with a length of 0.</span></span> <span data-ttu-id="1d043-110">メソッドは、スタック トレース情報を取得できませんが場合、戻り値は`E_FAIL`列挙子は返されません。</span><span class="sxs-lookup"><span data-stu-id="1d043-110">If the method is unable to retrieve stack trace information, the return value is `E_FAIL` and no enumerator is returned.</span></span>  
  
 <span data-ttu-id="1d043-111">[ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)オブジェクトはスタック トレース データをデコードの処理、`_stackTrace`例外オブジェクトのフィールド。</span><span class="sxs-lookup"><span data-stu-id="1d043-111">The [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) object is responsible for decoding the stack trace data from the `_stackTrace` field of the exception object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d043-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="1d043-112">Requirements</span></span>  
 <span data-ttu-id="1d043-113">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d043-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d043-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1d043-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1d043-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1d043-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1d043-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d043-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d043-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="1d043-117">See also</span></span>

- [<span data-ttu-id="1d043-118">ICorDebugExceptionObjectValue インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1d043-118">ICorDebugExceptionObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-interface.md)
- [<span data-ttu-id="1d043-119">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1d043-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
