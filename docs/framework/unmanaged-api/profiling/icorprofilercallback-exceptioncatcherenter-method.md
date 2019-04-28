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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a9b47e1d1bfa1d8f6c970e95fe25f62a690d3b91
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61598209"
---
# <a name="icorprofilercallbackexceptioncatcherenter-method"></a><span data-ttu-id="69e1c-102">ICorProfilerCallback::ExceptionCatcherEnter メソッド</span><span class="sxs-lookup"><span data-stu-id="69e1c-102">ICorProfilerCallback::ExceptionCatcherEnter Method</span></span>
<span data-ttu-id="69e1c-103">適切な制御が渡されることをプロファイラーに通知`catch`ブロックします。</span><span class="sxs-lookup"><span data-stu-id="69e1c-103">Notifies the profiler that control is being passed to the appropriate `catch` block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69e1c-104">構文</span><span class="sxs-lookup"><span data-stu-id="69e1c-104">Syntax</span></span>  
  
```  
HRESULT ExceptionCatcherEnter(  
    [in] FunctionID functionId,  
    [in] ObjectID   objectId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="69e1c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="69e1c-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="69e1c-106">[in]格納されている関数の識別子、`catch`ブロックします。</span><span class="sxs-lookup"><span data-stu-id="69e1c-106">[in] The identifier of the function containing the `catch` block.</span></span>  
  
 `objectId`  
 <span data-ttu-id="69e1c-107">[in]処理中の例外の識別子。</span><span class="sxs-lookup"><span data-stu-id="69e1c-107">[in] The identifier of the exception being handled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="69e1c-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="69e1c-108">Remarks</span></span>  
 <span data-ttu-id="69e1c-109">`ExceptionCatcherEnter` Catch ポイントが・ イン タイム (JIT) コンパイラでコンパイルされたコードの場合にのみ、メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="69e1c-109">The `ExceptionCatcherEnter` method is called only if the catch point is in code compiled with the just-in-time (JIT) compiler.</span></span> <span data-ttu-id="69e1c-110">アンマネージ コードまたはランタイムの内部のコードでキャッチされた例外には、この通知は呼び出しません。</span><span class="sxs-lookup"><span data-stu-id="69e1c-110">An exception that is caught in unmanaged code or in the internal code of the runtime will not call this notification.</span></span> <span data-ttu-id="69e1c-111">`objectId`ガベージ コレクションからオブジェクトが移動がでしたので、値をもう一度渡す、`ExceptionThrown`通知します。</span><span class="sxs-lookup"><span data-stu-id="69e1c-111">The `objectId` value is passed again since a garbage collection could have moved the object since the `ExceptionThrown` notification.</span></span>  
  
 <span data-ttu-id="69e1c-112">プロファイラーでは、スタックはガベージ コレクションを許可する状態にできない可能性がありますので、このメソッドの実装でブロックしないでくださいし、そのため、プリエンプティブなガベージ コレクションを有効にできません。</span><span class="sxs-lookup"><span data-stu-id="69e1c-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="69e1c-113">ここで、プロファイラーをブロックする場合とは、ガベージ コレクションが試行されると、ランタイムがこのコールバックが戻るまでブロックされます。</span><span class="sxs-lookup"><span data-stu-id="69e1c-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="69e1c-114">このメソッドのプロファイラーの実装には、任意の方法で管理されているメモリの割り当てが発生またはマネージ コードを呼び出さないでください。</span><span class="sxs-lookup"><span data-stu-id="69e1c-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69e1c-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="69e1c-115">Requirements</span></span>  
 <span data-ttu-id="69e1c-116">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="69e1c-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69e1c-117">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="69e1c-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="69e1c-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="69e1c-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="69e1c-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69e1c-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69e1c-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="69e1c-120">See also</span></span>

- [<span data-ttu-id="69e1c-121">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="69e1c-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="69e1c-122">ExceptionCatcherLeave メソッド</span><span class="sxs-lookup"><span data-stu-id="69e1c-122">ExceptionCatcherLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)
