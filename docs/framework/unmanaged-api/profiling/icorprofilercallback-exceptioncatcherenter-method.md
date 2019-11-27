---
title: ICorProfilerCallback::ExceptionCatcherEnter メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionCatcherEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCatcherEnter
helpviewer_keywords:
- ICorProfilerCallback::ExceptionCatcherEnter method [.NET Framework profiling]
- ExceptionCatcherEnter method [.NET Framework profiling]
ms.assetid: 41462329-a648-46f0-ae6d-728b94c31aa9
topic_type:
- apiref
ms.openlocfilehash: 9c9cd0b042dc22f35c38e349ab8881dafc602731
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445022"
---
# <a name="icorprofilercallbackexceptioncatcherenter-method"></a><span data-ttu-id="c2cd5-102">ICorProfilerCallback::ExceptionCatcherEnter メソッド</span><span class="sxs-lookup"><span data-stu-id="c2cd5-102">ICorProfilerCallback::ExceptionCatcherEnter Method</span></span>
<span data-ttu-id="c2cd5-103">適切な `catch` ブロックに制御が渡されていることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="c2cd5-103">Notifies the profiler that control is being passed to the appropriate `catch` block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2cd5-104">構文</span><span class="sxs-lookup"><span data-stu-id="c2cd5-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCatcherEnter(  
    [in] FunctionID functionId,  
    [in] ObjectID   objectId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2cd5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c2cd5-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="c2cd5-106">から`catch` ブロックを格納している関数の識別子。</span><span class="sxs-lookup"><span data-stu-id="c2cd5-106">[in] The identifier of the function containing the `catch` block.</span></span>  
  
 `objectId`  
 <span data-ttu-id="c2cd5-107">から処理されている例外の識別子。</span><span class="sxs-lookup"><span data-stu-id="c2cd5-107">[in] The identifier of the exception being handled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2cd5-108">コメント</span><span class="sxs-lookup"><span data-stu-id="c2cd5-108">Remarks</span></span>  
 <span data-ttu-id="c2cd5-109">`ExceptionCatcherEnter` メソッドは、catch ポイントが just-in-time (JIT) コンパイラを使用してコンパイルされたコード内にある場合にのみ呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="c2cd5-109">The `ExceptionCatcherEnter` method is called only if the catch point is in code compiled with the just-in-time (JIT) compiler.</span></span> <span data-ttu-id="c2cd5-110">アンマネージコードまたはランタイムの内部コードでキャッチされた例外は、この通知を呼び出しません。</span><span class="sxs-lookup"><span data-stu-id="c2cd5-110">An exception that is caught in unmanaged code or in the internal code of the runtime will not call this notification.</span></span> <span data-ttu-id="c2cd5-111">`objectId` 値は、ガベージコレクションが `ExceptionThrown` 通知以降にオブジェクトを移動した可能性があるため、再度渡されます。</span><span class="sxs-lookup"><span data-stu-id="c2cd5-111">The `objectId` value is passed again since a garbage collection could have moved the object since the `ExceptionThrown` notification.</span></span>  
  
 <span data-ttu-id="c2cd5-112">プロファイラーは、このメソッドの実装でブロックしないでください。スタックがガベージコレクションを許可する状態にならないため、プリエンプティブガベージコレクションを有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="c2cd5-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="c2cd5-113">プロファイラーがここでブロックし、ガベージコレクションを実行しようとすると、このコールバックが戻るまでランタイムはブロックします。</span><span class="sxs-lookup"><span data-stu-id="c2cd5-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="c2cd5-114">プロファイラーによるこのメソッドの実装では、マネージコードを呼び出さないようにするか、マネージメモリ割り当てを発生させることはできません。</span><span class="sxs-lookup"><span data-stu-id="c2cd5-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2cd5-115">要件</span><span class="sxs-lookup"><span data-stu-id="c2cd5-115">Requirements</span></span>  
 <span data-ttu-id="c2cd5-116">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2cd5-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2cd5-117">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c2cd5-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c2cd5-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2cd5-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2cd5-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2cd5-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2cd5-120">参照</span><span class="sxs-lookup"><span data-stu-id="c2cd5-120">See also</span></span>

- [<span data-ttu-id="c2cd5-121">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c2cd5-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="c2cd5-122">ExceptionCatcherLeave メソッド</span><span class="sxs-lookup"><span data-stu-id="c2cd5-122">ExceptionCatcherLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)
