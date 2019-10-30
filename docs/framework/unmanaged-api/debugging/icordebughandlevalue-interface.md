---
title: ICorDebugHandleValue インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugHandleValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHandleValue
helpviewer_keywords:
- ICorDebugHandleValue interface [.NET Framework debugging]
ms.assetid: 66fcd2b8-ac66-414b-83a8-75a925e17772
topic_type:
- apiref
ms.openlocfilehash: 94472e84b73cdffe09505088b1e7fbc20a209bc3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138477"
---
# <a name="icordebughandlevalue-interface"></a><span data-ttu-id="5d1dd-102">ICorDebugHandleValue インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5d1dd-102">ICorDebugHandleValue Interface</span></span>

<span data-ttu-id="5d1dd-103">デバッガーがガベージコレクションのハンドルを作成した参照値を表す、値のサブクラス。</span><span class="sxs-lookup"><span data-stu-id="5d1dd-103">A subclass of ICorDebugReferenceValue that represents a reference value to which the debugger has created a handle for garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5d1dd-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="5d1dd-104">Methods</span></span>  
  
|<span data-ttu-id="5d1dd-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="5d1dd-105">Method</span></span>|<span data-ttu-id="5d1dd-106">説明</span><span class="sxs-lookup"><span data-stu-id="5d1dd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5d1dd-107">Dispose メソッド</span><span class="sxs-lookup"><span data-stu-id="5d1dd-107">Dispose Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-dispose-method.md)|<span data-ttu-id="5d1dd-108">インターフェイスポインターを明示的に解放せずに、この `ICorDebugHandleValue` オブジェクトが参照するハンドルを解放します。</span><span class="sxs-lookup"><span data-stu-id="5d1dd-108">Releases the handle referenced by this `ICorDebugHandleValue` object without explicitly releasing the interface pointer.</span></span>|  
|[<span data-ttu-id="5d1dd-109">GetHandleType メソッド</span><span class="sxs-lookup"><span data-stu-id="5d1dd-109">GetHandleType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-gethandletype-method.md)|<span data-ttu-id="5d1dd-110">この `ICorDebugHandleValue`によって参照されるハンドルの種類を示す CorDebugHandleType 値を取得します。</span><span class="sxs-lookup"><span data-stu-id="5d1dd-110">Gets a CorDebugHandleType value that describes the kind of handle referenced by this `ICorDebugHandleValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d1dd-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="5d1dd-111">Remarks</span></span>  
 <span data-ttu-id="5d1dd-112">デバッグ対象のコードの実行が中断された場合、`ICorDebugReferenceValue` オブジェクトは無効になります。</span><span class="sxs-lookup"><span data-stu-id="5d1dd-112">An `ICorDebugReferenceValue` object is invalidated by a break in the execution of debugged code.</span></span> <span data-ttu-id="5d1dd-113">`ICorDebugHandleValue` は、明示的に解放されるまで、中断と継続を通じて参照を保持します。</span><span class="sxs-lookup"><span data-stu-id="5d1dd-113">An `ICorDebugHandleValue` maintains its reference through breaks and continuations, until it is explicitly released.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5d1dd-114">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="5d1dd-114">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d1dd-115">［要件］</span><span class="sxs-lookup"><span data-stu-id="5d1dd-115">Requirements</span></span>  
 <span data-ttu-id="5d1dd-116">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d1dd-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d1dd-117">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5d1dd-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5d1dd-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5d1dd-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5d1dd-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d1dd-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d1dd-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="5d1dd-120">See also</span></span>

- [<span data-ttu-id="5d1dd-121">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5d1dd-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
