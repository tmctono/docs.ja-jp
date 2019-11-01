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
ms.openlocfilehash: 9f54fdfe16bc24394503ba6f5a9b906a32ec2c8b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73091104"
---
# <a name="icordebugexceptionobjectvalueenumerateexceptioncallstack-method"></a><span data-ttu-id="96425-102">ICorDebugExceptionObjectValue::EnumerateExceptionCallStack メソッド</span><span class="sxs-lookup"><span data-stu-id="96425-102">ICorDebugExceptionObjectValue::EnumerateExceptionCallStack Method</span></span>
<span data-ttu-id="96425-103">例外オブジェクトに埋め込まれている呼び出し履歴に対する列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="96425-103">Gets an enumerator to the call stack embedded in an exception object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96425-104">構文</span><span class="sxs-lookup"><span data-stu-id="96425-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateExceptionCallStack(  
    [out] ICorDebugExceptionObjectCallStackEnum **ppCallStackEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="96425-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="96425-105">Parameters</span></span>  
 <span data-ttu-id="96425-106">ppCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="96425-106">ppCallStackEnum</span></span>  
 <span data-ttu-id="96425-107">入出力マネージ例外オブジェクトのスタックトレース列挙[ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)子である、というコードのアドレスへのポインターを示します。</span><span class="sxs-lookup"><span data-stu-id="96425-107">[out] A pointer to the address of an [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) interface object that is a stack trace enumerator for a managed exception object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96425-108">コメント</span><span class="sxs-lookup"><span data-stu-id="96425-108">Remarks</span></span>  
 <span data-ttu-id="96425-109">呼び出し履歴情報が使用できない場合、メソッドは `S_OK`を返します。また、は、値が0の有効な列挙[子です。](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="96425-109">If no call stack information is available, the method returns `S_OK`, and [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) is a valid enumerator with a length of 0.</span></span> <span data-ttu-id="96425-110">メソッドがスタックトレース情報を取得できない場合、戻り値は `E_FAIL`、列挙子は返されません。</span><span class="sxs-lookup"><span data-stu-id="96425-110">If the method is unable to retrieve stack trace information, the return value is `E_FAIL` and no enumerator is returned.</span></span>  
  
 <span data-ttu-id="96425-111">は、例外オブジェクトの `_stackTrace` フィールドからスタックトレースデータをデコードするために、のオブジェクトを[使用します](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="96425-111">The [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) object is responsible for decoding the stack trace data from the `_stackTrace` field of the exception object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96425-112">要件</span><span class="sxs-lookup"><span data-stu-id="96425-112">Requirements</span></span>  
 <span data-ttu-id="96425-113">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="96425-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96425-114">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="96425-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="96425-115">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="96425-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="96425-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96425-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96425-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="96425-117">See also</span></span>

- [<span data-ttu-id="96425-118">ICorDebugExceptionObjectValue インターフェイス</span><span class="sxs-lookup"><span data-stu-id="96425-118">ICorDebugExceptionObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-interface.md)
- [<span data-ttu-id="96425-119">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="96425-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
