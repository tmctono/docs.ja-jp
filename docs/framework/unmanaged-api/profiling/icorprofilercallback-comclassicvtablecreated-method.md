---
title: ICorProfilerCallback::COMClassicVTableCreated メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.COMClassicVTableCreated
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::COMClassicVTableCreated
helpviewer_keywords:
- COMClassicVTableCreated method [.NET Framework profiling]
- ICorProfilerCallback::COMClassicVTableCreated method [.NET Framework profiling]
ms.assetid: 6e1834ab-c359-498a-b10b-984ae23cdda4
topic_type:
- apiref
ms.openlocfilehash: 808c26f53c4089248420280a43c88a1b3af0dad9
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866547"
---
# <a name="icorprofilercallbackcomclassicvtablecreated-method"></a><span data-ttu-id="daaeb-102">ICorProfilerCallback::COMClassicVTableCreated メソッド</span><span class="sxs-lookup"><span data-stu-id="daaeb-102">ICorProfilerCallback::COMClassicVTableCreated Method</span></span>
<span data-ttu-id="daaeb-103">指定した IID およびクラスの COM 相互運用機能の vtable が作成されたことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="daaeb-103">Notifies the profiler that a COM interop vtable for the specified IID and class has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="daaeb-104">構文</span><span class="sxs-lookup"><span data-stu-id="daaeb-104">Syntax</span></span>  
  
```cpp  
HRESULT COMClassicVTableCreated(  
    [in] ClassID wrappedClassId,  
    [in] REFGUID implementedIID,  
    [in] void    *pVTable,  
    [in] ULONG   cSlots);  
```  
  
## <a name="parameters"></a><span data-ttu-id="daaeb-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="daaeb-105">Parameters</span></span>

- `wrappedClasId`

  <span data-ttu-id="daaeb-106">\[] には、vtable が作成されたクラスの ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="daaeb-106">\[in] The ID of the class for which the vtable has been created.</span></span>

- `implementedIID`

  <span data-ttu-id="daaeb-107">\[] クラスによって実装されるインターフェイスの ID。</span><span class="sxs-lookup"><span data-stu-id="daaeb-107">\[in] The ID of the interface implemented by the class.</span></span> <span data-ttu-id="daaeb-108">この値は、インターフェイスが内部でのみ使用されている場合は NULL になります。</span><span class="sxs-lookup"><span data-stu-id="daaeb-108">This value may be NULL if the interface is internal only.</span></span>

- `pVTable`

  <span data-ttu-id="daaeb-109">\[] には、vtable の先頭へのポインターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="daaeb-109">\[in] A pointer to the start of the vtable.</span></span>

- `cSlots`

  <span data-ttu-id="daaeb-110">\[] には、vtable 内のスロットの数を指定します。</span><span class="sxs-lookup"><span data-stu-id="daaeb-110">\[in] The number of slots that are in the vtable.</span></span>

## <a name="remarks"></a><span data-ttu-id="daaeb-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="daaeb-111">Remarks</span></span>  
 <span data-ttu-id="daaeb-112">プロファイラーは、このメソッドの実装でブロックしないでください。スタックがガベージコレクションを許可する状態にならないため、プリエンプティブガベージコレクションを有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="daaeb-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="daaeb-113">プロファイラーがここでブロックし、ガベージコレクションを実行しようとすると、このコールバックが戻るまでランタイムはブロックします。</span><span class="sxs-lookup"><span data-stu-id="daaeb-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="daaeb-114">プロファイラーによるこのメソッドの実装では、マネージコードを呼び出さないようにするか、マネージメモリ割り当てを発生させることはできません。</span><span class="sxs-lookup"><span data-stu-id="daaeb-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="daaeb-115">要件</span><span class="sxs-lookup"><span data-stu-id="daaeb-115">Requirements</span></span>  
 <span data-ttu-id="daaeb-116">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="daaeb-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="daaeb-117">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="daaeb-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="daaeb-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="daaeb-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="daaeb-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="daaeb-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="daaeb-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="daaeb-120">See also</span></span>

- [<span data-ttu-id="daaeb-121">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="daaeb-121">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="daaeb-122">COMClassicVTableDestroyed メソッド</span><span class="sxs-lookup"><span data-stu-id="daaeb-122">COMClassicVTableDestroyed Method</span></span>](icorprofilercallback-comclassicvtabledestroyed-method.md)
