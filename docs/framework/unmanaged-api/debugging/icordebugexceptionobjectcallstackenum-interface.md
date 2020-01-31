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
ms.openlocfilehash: 9d98bccdfb83cec547b185693c28f25017d3225f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782805"
---
# <a name="icordebugexceptionobjectcallstackenum-interface"></a><span data-ttu-id="c83fe-102">ICorDebugExceptionObjectCallStackEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c83fe-102">ICorDebugExceptionObjectCallStackEnum Interface</span></span>
<span data-ttu-id="c83fe-103">例外オブジェクトに埋め込まれているコール スタックの情報の列挙子を提供します。</span><span class="sxs-lookup"><span data-stu-id="c83fe-103">Provides an enumerator for call stack information that is embedded in an exception object.</span></span> <span data-ttu-id="c83fe-104">このインターフェイスは、ICorDebugEnum インターフェイスのサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="c83fe-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c83fe-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="c83fe-105">Methods</span></span>  
  
|<span data-ttu-id="c83fe-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="c83fe-106">Method</span></span>|<span data-ttu-id="c83fe-107">説明</span><span class="sxs-lookup"><span data-stu-id="c83fe-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c83fe-108">いい Exceptionobjectcallstackenum:: Next</span><span class="sxs-lookup"><span data-stu-id="c83fe-108">ICorDebugExceptionObjectCallStackEnum::Next</span></span>](icordebugexceptionobjectcallstackenum-next-method.md)|<span data-ttu-id="c83fe-109">例外オブジェクトの呼び出し履歴に関する情報を格納している、指定した数の[CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md)オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="c83fe-109">Gets a specified number of [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) objects that contain information about an exception object's call stack.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c83fe-110">コメント</span><span class="sxs-lookup"><span data-stu-id="c83fe-110">Remarks</span></span>  
 <span data-ttu-id="c83fe-111">`ICorDebugExceptionObjectCallStackEnum` インターフェイスは、ICorDebugEnum インターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="c83fe-111">The `ICorDebugExceptionObjectCallStackEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="c83fe-112">[CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md)オブジェクトには、EnumerateExceptionCallStack メソッドを呼び出すことによって[値](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md)が設定されます。 `ICorDebugExceptionObjectCallStackEnum`</span><span class="sxs-lookup"><span data-stu-id="c83fe-112">An `ICorDebugExceptionObjectCallStackEnum` instance is populated with [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) objects by calling the [ICorDebugExceptionObjectValue::EnumerateExceptionCallStack](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md) method.</span></span> <span data-ttu-id="c83fe-113">コレクション内のコールスタック項目を列挙するには、[次](icordebugexceptionobjectcallstackenum-next-method.md)のように指定します。</span><span class="sxs-lookup"><span data-stu-id="c83fe-113">The call stack items in the collection can be enumerated by calling the [ICorDebugExceptionObjectCallStackEnum::Next](icordebugexceptionobjectcallstackenum-next-method.md) method</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c83fe-114">要件</span><span class="sxs-lookup"><span data-stu-id="c83fe-114">Requirements</span></span>  
 <span data-ttu-id="c83fe-115">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c83fe-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c83fe-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c83fe-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c83fe-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c83fe-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c83fe-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c83fe-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c83fe-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="c83fe-119">See also</span></span>

- [<span data-ttu-id="c83fe-120">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c83fe-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="c83fe-121">デバッグ</span><span class="sxs-lookup"><span data-stu-id="c83fe-121">Debugging</span></span>](index.md)
