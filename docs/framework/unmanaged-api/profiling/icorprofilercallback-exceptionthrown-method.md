---
title: ICorProfilerCallback::ExceptionThrown メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionThrown
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionThrown
helpviewer_keywords:
- ExceptionThrown method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionThrown method [.NET Framework profiling]
ms.assetid: f1a23f3b-ac21-4905-8abf-8ea59f15af53
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cb95c11900b84b78a3f862bcb73f0700aaabeeaa
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67755984"
---
# <a name="icorprofilercallbackexceptionthrown-method"></a><span data-ttu-id="8e9ab-102">ICorProfilerCallback::ExceptionThrown メソッド</span><span class="sxs-lookup"><span data-stu-id="8e9ab-102">ICorProfilerCallback::ExceptionThrown Method</span></span>
<span data-ttu-id="8e9ab-103">例外がスローされたことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="8e9ab-103">Notifies the profiler that an exception has been thrown.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8e9ab-104">例外がマネージ コードに達した場合にのみ、この関数が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="8e9ab-104">This function is called only if the exception reaches managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e9ab-105">構文</span><span class="sxs-lookup"><span data-stu-id="8e9ab-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionThrown(  
    [in] ObjectID thrownObjectId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8e9ab-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8e9ab-106">Parameters</span></span>  
 `thrownObjectId`  
 <span data-ttu-id="8e9ab-107">[in]スローされる例外の原因となったオブジェクトの ID。</span><span class="sxs-lookup"><span data-stu-id="8e9ab-107">[in] The ID of the object that caused the exception to be thrown.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8e9ab-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="8e9ab-108">Remarks</span></span>  
 <span data-ttu-id="8e9ab-109">プロファイラーでは、スタックはガベージ コレクションを許可する状態にできない可能性がありますので、このメソッドの実装でブロックしないでくださいし、そのため、プリエンプティブなガベージ コレクションを有効にできません。</span><span class="sxs-lookup"><span data-stu-id="8e9ab-109">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="8e9ab-110">ここで、プロファイラーをブロックする場合とは、ガベージ コレクションが試行されると、ランタイムがこのコールバックが戻るまでブロックされます。</span><span class="sxs-lookup"><span data-stu-id="8e9ab-110">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="8e9ab-111">このメソッドのプロファイラーの実装には、任意の方法で管理されているメモリの割り当てが発生またはマネージ コードを呼び出さないでください。</span><span class="sxs-lookup"><span data-stu-id="8e9ab-111">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e9ab-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="8e9ab-112">Requirements</span></span>  
 <span data-ttu-id="8e9ab-113">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e9ab-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e9ab-114">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8e9ab-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8e9ab-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8e9ab-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8e9ab-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e9ab-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e9ab-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="8e9ab-117">See also</span></span>

- [<span data-ttu-id="8e9ab-118">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8e9ab-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
