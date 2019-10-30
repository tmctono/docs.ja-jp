---
title: ICorDebugExceptionObjectCallStackEnum インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectCallStackEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectCallStackEnum
helpviewer_keywords:
- ICorDebugExceptionObjectCallStackEnum interface [.NET Framework debugging]
ms.assetid: 39dffa18-c71b-48c4-b11d-e814631ab1e9
topic_type:
- apiref
ms.openlocfilehash: 99a700270794ca92356cb9d134cb869d456199f9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73084428"
---
# <a name="icordebugexceptionobjectcallstackenum-interface"></a><span data-ttu-id="2dfa0-102">ICorDebugExceptionObjectCallStackEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2dfa0-102">ICorDebugExceptionObjectCallStackEnum Interface</span></span>
<span data-ttu-id="2dfa0-103">例外オブジェクトに埋め込まれているコール スタックの情報の列挙子を提供します。</span><span class="sxs-lookup"><span data-stu-id="2dfa0-103">Provides an enumerator for call stack information that is embedded in an exception object.</span></span> <span data-ttu-id="2dfa0-104">このインターフェイスは、ICorDebugEnum インターフェイスのサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="2dfa0-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2dfa0-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="2dfa0-105">Methods</span></span>  
  
|<span data-ttu-id="2dfa0-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="2dfa0-106">Method</span></span>|<span data-ttu-id="2dfa0-107">説明</span><span class="sxs-lookup"><span data-stu-id="2dfa0-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2dfa0-108">いい Exceptionobjectcallstackenum:: Next</span><span class="sxs-lookup"><span data-stu-id="2dfa0-108">ICorDebugExceptionObjectCallStackEnum::Next</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-next-method.md)|<span data-ttu-id="2dfa0-109">例外オブジェクトの呼び出し履歴に関する情報を格納している、指定した数の[CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md)オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="2dfa0-109">Gets a specified number of [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) objects that contain information about an exception object's call stack.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2dfa0-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="2dfa0-110">Remarks</span></span>  
 <span data-ttu-id="2dfa0-111">`ICorDebugExceptionObjectCallStackEnum` インターフェイスは、ICorDebugEnum インターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="2dfa0-111">The `ICorDebugExceptionObjectCallStackEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="2dfa0-112">[CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md)オブジェクトには、EnumerateExceptionCallStack メソッドを呼び出すことによって[値](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md)が設定されます。 `ICorDebugExceptionObjectCallStackEnum`</span><span class="sxs-lookup"><span data-stu-id="2dfa0-112">An `ICorDebugExceptionObjectCallStackEnum` instance is populated with [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) objects by calling the [ICorDebugExceptionObjectValue::EnumerateExceptionCallStack](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md) method.</span></span> <span data-ttu-id="2dfa0-113">コレクション内のコールスタック項目を列挙するには、[次](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-next-method.md)のように指定します。</span><span class="sxs-lookup"><span data-stu-id="2dfa0-113">The call stack items in the collection can be enumerated by calling the [ICorDebugExceptionObjectCallStackEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-next-method.md) method</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2dfa0-114">［要件］</span><span class="sxs-lookup"><span data-stu-id="2dfa0-114">Requirements</span></span>  
 <span data-ttu-id="2dfa0-115">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dfa0-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2dfa0-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2dfa0-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2dfa0-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2dfa0-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2dfa0-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2dfa0-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dfa0-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="2dfa0-119">See also</span></span>

- [<span data-ttu-id="2dfa0-120">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2dfa0-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="2dfa0-121">デバッグ</span><span class="sxs-lookup"><span data-stu-id="2dfa0-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
