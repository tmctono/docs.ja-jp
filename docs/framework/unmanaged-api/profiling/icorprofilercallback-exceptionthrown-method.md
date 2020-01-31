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
ms.openlocfilehash: b1799472c4923aaccfabeae459ad72f6ae94c80d
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866378"
---
# <a name="icorprofilercallbackexceptionthrown-method"></a><span data-ttu-id="c26e0-102">ICorProfilerCallback::ExceptionThrown メソッド</span><span class="sxs-lookup"><span data-stu-id="c26e0-102">ICorProfilerCallback::ExceptionThrown Method</span></span>
<span data-ttu-id="c26e0-103">例外がスローされたことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="c26e0-103">Notifies the profiler that an exception has been thrown.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c26e0-104">この関数は、例外がマネージコードに到達した場合にのみ呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="c26e0-104">This function is called only if the exception reaches managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c26e0-105">構文</span><span class="sxs-lookup"><span data-stu-id="c26e0-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionThrown(  
    [in] ObjectID thrownObjectId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c26e0-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c26e0-106">Parameters</span></span>

- `thrownObjectId`

  <span data-ttu-id="c26e0-107">\[] には、例外がスローされる原因となったオブジェクトの ID が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c26e0-107">\[in] The ID of the object that caused the exception to be thrown.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="c26e0-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="c26e0-108">Remarks</span></span>  
 <span data-ttu-id="c26e0-109">プロファイラーは、このメソッドの実装でブロックしないでください。スタックがガベージコレクションを許可する状態にならないため、プリエンプティブガベージコレクションを有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="c26e0-109">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="c26e0-110">プロファイラーがここでブロックし、ガベージコレクションを実行しようとすると、このコールバックが戻るまでランタイムはブロックします。</span><span class="sxs-lookup"><span data-stu-id="c26e0-110">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="c26e0-111">プロファイラーによるこのメソッドの実装では、マネージコードを呼び出さないようにするか、マネージメモリ割り当てを発生させることはできません。</span><span class="sxs-lookup"><span data-stu-id="c26e0-111">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c26e0-112">要件</span><span class="sxs-lookup"><span data-stu-id="c26e0-112">Requirements</span></span>  
 <span data-ttu-id="c26e0-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c26e0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c26e0-114">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c26e0-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c26e0-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c26e0-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c26e0-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c26e0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c26e0-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="c26e0-117">See also</span></span>

- [<span data-ttu-id="c26e0-118">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c26e0-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
