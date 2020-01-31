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
ms.openlocfilehash: 38de810509f15cf93475eb000837892b99684fc9
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782743"
---
# <a name="icordebugexceptionobjectcallstackenumnext-method"></a><span data-ttu-id="df954-102">ICorDebugExceptionObjectCallStackEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="df954-102">ICorDebugExceptionObjectCallStackEnum::Next Method</span></span>
<span data-ttu-id="df954-103">例外オブジェクトの呼び出し履歴の情報を格納している、指定した数の[CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md)インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="df954-103">Gets the specified number of [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) instances that contain information from an exception object's call stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df954-104">構文</span><span class="sxs-lookup"><span data-stu-id="df954-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] CorDebugExceptionObjectStackFrame values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df954-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="df954-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="df954-106">から取得する[CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md)インスタンスの数。</span><span class="sxs-lookup"><span data-stu-id="df954-106">[in] The number of [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="df954-107">入出力ポインターの配列。それぞれが[CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md)オブジェクトを指します。</span><span class="sxs-lookup"><span data-stu-id="df954-107">[out] An array of pointers, each of which points to a [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="df954-108">入出力実際に返された[CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md)インスタンスの数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="df954-108">[out] A pointer to the number of [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) instances actually returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="df954-109">コメント</span><span class="sxs-lookup"><span data-stu-id="df954-109">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df954-110">要件</span><span class="sxs-lookup"><span data-stu-id="df954-110">Requirements</span></span>  
 <span data-ttu-id="df954-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df954-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df954-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="df954-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="df954-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="df954-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="df954-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df954-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df954-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="df954-115">See also</span></span>

- [<span data-ttu-id="df954-116">ICorDebugExceptionObjectCallStackEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="df954-116">ICorDebugExceptionObjectCallStackEnum Interface</span></span>](icordebugexceptionobjectcallstackenum-interface.md)
- [<span data-ttu-id="df954-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="df954-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
