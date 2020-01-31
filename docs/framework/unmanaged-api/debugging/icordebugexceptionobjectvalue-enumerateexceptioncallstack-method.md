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
ms.openlocfilehash: 57eb284bfe39ce92b2d6c03a2aeb4ae84d6aba91
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788675"
---
# <a name="icordebugexceptionobjectvalueenumerateexceptioncallstack-method"></a><span data-ttu-id="9bcf0-102">ICorDebugExceptionObjectValue::EnumerateExceptionCallStack メソッド</span><span class="sxs-lookup"><span data-stu-id="9bcf0-102">ICorDebugExceptionObjectValue::EnumerateExceptionCallStack Method</span></span>
<span data-ttu-id="9bcf0-103">例外オブジェクトに埋め込まれている呼び出し履歴に対する列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="9bcf0-103">Gets an enumerator to the call stack embedded in an exception object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9bcf0-104">構文</span><span class="sxs-lookup"><span data-stu-id="9bcf0-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateExceptionCallStack(  
    [out] ICorDebugExceptionObjectCallStackEnum **ppCallStackEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9bcf0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9bcf0-105">Parameters</span></span>  
 <span data-ttu-id="9bcf0-106">ppCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="9bcf0-106">ppCallStackEnum</span></span>  
 <span data-ttu-id="9bcf0-107">入出力マネージ例外オブジェクトの[スタックトレース](icordebugexceptionobjectcallstackenum-interface.md)列挙子である、というコードのアドレスへのポインターを示します。
</span><span class="sxs-lookup"><span data-stu-id="9bcf0-107">[out] A pointer to the address of an [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md) interface object that is a stack trace enumerator for a managed exception object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9bcf0-108">コメント</span><span class="sxs-lookup"><span data-stu-id="9bcf0-108">Remarks</span></span>  
 <span data-ttu-id="9bcf0-109">呼び出し履歴情報が使用できない場合、メソッドは `S_OK`を返します。また、は、値が0の有効な列挙[子です。](icordebugexceptionobjectcallstackenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9bcf0-109">If no call stack information is available, the method returns `S_OK`, and [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md) is a valid enumerator with a length of 0.</span></span> <span data-ttu-id="9bcf0-110">メソッドがスタックトレース情報を取得できない場合、戻り値は `E_FAIL`、列挙子は返されません。</span><span class="sxs-lookup"><span data-stu-id="9bcf0-110">If the method is unable to retrieve stack trace information, the return value is `E_FAIL` and no enumerator is returned.</span></span>  
  
 <span data-ttu-id="9bcf0-111">は、例外オブジェクトの `_stackTrace` フィールドからスタックトレースデータをデコードするために、のオブジェクトを[使用します](icordebugexceptionobjectcallstackenum-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="9bcf0-111">The [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md) object is responsible for decoding the stack trace data from the `_stackTrace` field of the exception object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9bcf0-112">要件</span><span class="sxs-lookup"><span data-stu-id="9bcf0-112">Requirements</span></span>  
 <span data-ttu-id="9bcf0-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9bcf0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9bcf0-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9bcf0-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9bcf0-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9bcf0-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9bcf0-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9bcf0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bcf0-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="9bcf0-117">See also</span></span>

- [<span data-ttu-id="9bcf0-118">ICorDebugExceptionObjectValue インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9bcf0-118">ICorDebugExceptionObjectValue Interface</span></span>](icordebugexceptionobjectvalue-interface.md)
- [<span data-ttu-id="9bcf0-119">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9bcf0-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
