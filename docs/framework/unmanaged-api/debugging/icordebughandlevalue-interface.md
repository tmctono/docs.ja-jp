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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9a9eb63e681b47f058901b0ff002015baffe6048
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59117444"
---
# <a name="icordebughandlevalue-interface"></a><span data-ttu-id="5698a-102">ICorDebugHandleValue インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5698a-102">ICorDebugHandleValue Interface</span></span>

<span data-ttu-id="5698a-103">参照値が、デバッガーにガベージ コレクションのハンドルが作成を表すサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="5698a-103">A subclass of ICorDebugReferenceValue that represents a reference value to which the debugger has created a handle for garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5698a-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="5698a-104">Methods</span></span>  
  
|<span data-ttu-id="5698a-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="5698a-105">Method</span></span>|<span data-ttu-id="5698a-106">説明</span><span class="sxs-lookup"><span data-stu-id="5698a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5698a-107">Dispose メソッド</span><span class="sxs-lookup"><span data-stu-id="5698a-107">Dispose Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-dispose-method.md)|<span data-ttu-id="5698a-108">これによって参照されるハンドルを解放`ICorDebugHandleValue`インターフェイス ポインターを明示的に解放しないままオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="5698a-108">Releases the handle referenced by this `ICorDebugHandleValue` object without explicitly releasing the interface pointer.</span></span>|  
|[<span data-ttu-id="5698a-109">GetHandleType メソッド</span><span class="sxs-lookup"><span data-stu-id="5698a-109">GetHandleType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-gethandletype-method.md)|<span data-ttu-id="5698a-110">これによって参照されるハンドルの種類を記述する CorDebugHandleType 値を取得します`ICorDebugHandleValue`します。</span><span class="sxs-lookup"><span data-stu-id="5698a-110">Gets a CorDebugHandleType value that describes the kind of handle referenced by this `ICorDebugHandleValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5698a-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="5698a-111">Remarks</span></span>  
 <span data-ttu-id="5698a-112">`ICorDebugReferenceValue`オブジェクトがデバッグ対象のコードの実行の中断によって無効にします。</span><span class="sxs-lookup"><span data-stu-id="5698a-112">An `ICorDebugReferenceValue` object is invalidated by a break in the execution of debugged code.</span></span> <span data-ttu-id="5698a-113">`ICorDebugHandleValue`明示的に解放されるまでの区切りと継続のうち、その参照を保持します。</span><span class="sxs-lookup"><span data-stu-id="5698a-113">An `ICorDebugHandleValue` maintains its reference through breaks and continuations, until it is explicitly released.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5698a-114">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="5698a-114">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5698a-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="5698a-115">Requirements</span></span>  
 <span data-ttu-id="5698a-116">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5698a-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5698a-117">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5698a-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5698a-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5698a-118">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="5698a-119">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="5698a-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5698a-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="5698a-120">See also</span></span>

- [<span data-ttu-id="5698a-121">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="5698a-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
