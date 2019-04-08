---
title: ICorDebugExceptionObjectCallStackEnum::Next メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectCallStackEnum::Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectCallStackEnum::Next
helpviewer_keywords:
- ICorDebugExceptionObjectCallStackEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugExceptionObjectCallStackEnum interface [.NET Framework debugging]
ms.assetid: 3328a2c0-1e48-4a54-802a-9b474cf82c21
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7c33f76b5eaa87c0b69497547732564921f662d5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59099470"
---
# <a name="icordebugexceptionobjectcallstackenumnext-method"></a><span data-ttu-id="0c602-102">ICorDebugExceptionObjectCallStackEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="0c602-102">ICorDebugExceptionObjectCallStackEnum::Next Method</span></span>
<span data-ttu-id="0c602-103">指定した数を取得[CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md)例外オブジェクトの呼び出し履歴から情報が含まれているインスタンス。</span><span class="sxs-lookup"><span data-stu-id="0c602-103">Gets the specified number of [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) instances that contain information from an exception object's call stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c602-104">構文</span><span class="sxs-lookup"><span data-stu-id="0c602-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] CorDebugExceptionObjectStackFrame values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c602-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0c602-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="0c602-106">[in]数[CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md)インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="0c602-106">[in] The number of [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="0c602-107">[out]それぞれが指すポインターの配列を[CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="0c602-107">[out] An array of pointers, each of which points to a [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="0c602-108">[out]数へのポインター [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md)インスタンスが実際に返されます。</span><span class="sxs-lookup"><span data-stu-id="0c602-108">[out] A pointer to the number of [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) instances actually returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c602-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="0c602-109">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c602-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="0c602-110">Requirements</span></span>  
 <span data-ttu-id="0c602-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c602-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c602-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0c602-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0c602-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0c602-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="0c602-114">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="0c602-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0c602-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="0c602-115">See also</span></span>

- [<span data-ttu-id="0c602-116">ICorDebugExceptionObjectCallStackEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0c602-116">ICorDebugExceptionObjectCallStackEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)
- [<span data-ttu-id="0c602-117">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="0c602-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
