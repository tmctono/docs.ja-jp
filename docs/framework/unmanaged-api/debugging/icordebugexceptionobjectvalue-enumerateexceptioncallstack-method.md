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
ms.openlocfilehash: db0e794953578fccd08428b730b3d7951e13bee3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59074080"
---
# <a name="icordebugexceptionobjectvalueenumerateexceptioncallstack-method"></a><span data-ttu-id="240f6-102">ICorDebugExceptionObjectValue::EnumerateExceptionCallStack メソッド</span><span class="sxs-lookup"><span data-stu-id="240f6-102">ICorDebugExceptionObjectValue::EnumerateExceptionCallStack Method</span></span>
<span data-ttu-id="240f6-103">呼び出し履歴を例外オブジェクトに埋め込まれている列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="240f6-103">Gets an enumerator to the call stack embedded in an exception object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="240f6-104">構文</span><span class="sxs-lookup"><span data-stu-id="240f6-104">Syntax</span></span>  
  
```  
HRESULT EnumerateExceptionCallStack(  
    [out] ICorDebugExceptionObjectCallStackEnum **ppCallStackEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="240f6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="240f6-105">Parameters</span></span>  
 <span data-ttu-id="240f6-106">ppCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="240f6-106">ppCallStackEnum</span></span>  
 <span data-ttu-id="240f6-107">[out]アドレスへのポインター、 [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)インターフェイス オブジェクトはマネージ例外オブジェクトのスタック トレースの列挙子です。</span><span class="sxs-lookup"><span data-stu-id="240f6-107">[out] A pointer to the address of an [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) interface object that is a stack trace enumerator for a managed exception object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="240f6-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="240f6-108">Remarks</span></span>  
 <span data-ttu-id="240f6-109">呼び出し履歴情報がないかどうか、メソッドを返します`S_OK`、および[ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)は長さ 0 の有効な列挙子です。</span><span class="sxs-lookup"><span data-stu-id="240f6-109">If no call stack information is available, the method returns `S_OK`, and [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) is a valid enumerator with a length of 0.</span></span> <span data-ttu-id="240f6-110">メソッドは、スタック トレース情報を取得できませんが場合、戻り値は`E_FAIL`列挙子は返されません。</span><span class="sxs-lookup"><span data-stu-id="240f6-110">If the method is unable to retrieve stack trace information, the return value is `E_FAIL` and no enumerator is returned.</span></span>  
  
 <span data-ttu-id="240f6-111">[ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)オブジェクトはスタック トレース データをデコードの処理、`_stackTrace`例外オブジェクトのフィールド。</span><span class="sxs-lookup"><span data-stu-id="240f6-111">The [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) object is responsible for decoding the stack trace data from the `_stackTrace` field of the exception object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="240f6-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="240f6-112">Requirements</span></span>  
 <span data-ttu-id="240f6-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="240f6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="240f6-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="240f6-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="240f6-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="240f6-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="240f6-116">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="240f6-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="240f6-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="240f6-117">See also</span></span>

- [<span data-ttu-id="240f6-118">ICorDebugExceptionObjectValue インターフェイス</span><span class="sxs-lookup"><span data-stu-id="240f6-118">ICorDebugExceptionObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-interface.md)
- [<span data-ttu-id="240f6-119">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="240f6-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
