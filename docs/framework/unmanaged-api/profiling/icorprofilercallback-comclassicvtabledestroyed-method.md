---
title: ICorProfilerCallback::COMClassicVTableDestroyed メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.COMClassicVTableDestroyed
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::COMClassicVTableDestroyed
helpviewer_keywords:
- ICorProfilerCallback::COMClassicVTableDestroyed method [.NET Framework profiling]
- COMClassicVTableDestroyed method [.NET Framework profiling]
ms.assetid: 29da20ca-bf39-4356-8099-d9c3ac3423a9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fffe8059a3be42a05d564773766023c6bbe4d56d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57467000"
---
# <a name="icorprofilercallbackcomclassicvtabledestroyed-method"></a><span data-ttu-id="6ca0a-102">ICorProfilerCallback::COMClassicVTableDestroyed メソッド</span><span class="sxs-lookup"><span data-stu-id="6ca0a-102">ICorProfilerCallback::COMClassicVTableDestroyed Method</span></span>
<span data-ttu-id="6ca0a-103">COM 相互運用機能の vtable が破棄されていることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="6ca0a-103">Notifies the profiler that a COM interop vtable is being destroyed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6ca0a-104">このコールバックは、シャット ダウンに近いに vtable の破壊が発生するので、発生することはありません。</span><span class="sxs-lookup"><span data-stu-id="6ca0a-104">This callback is likely never to occur, because the destruction of vtables occurs very close to shutdown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ca0a-105">構文</span><span class="sxs-lookup"><span data-stu-id="6ca0a-105">Syntax</span></span>  
  
```  
HRESULT COMClassicVTableDestroyed(  
    [in] ClassID wrappedClassId,  
    [in] REFGUID implementedIID,  
    [in] void    *pVTable);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6ca0a-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6ca0a-106">Parameters</span></span>  
 `wrappedClasId`  
 <span data-ttu-id="6ca0a-107">[in]この vtable が作成されたクラスの ID。</span><span class="sxs-lookup"><span data-stu-id="6ca0a-107">[in] The ID of the class for which this vtable was created.</span></span>  
  
 `implementedIID`  
 <span data-ttu-id="6ca0a-108">[in]クラスによって実装されるインターフェイスの ID。</span><span class="sxs-lookup"><span data-stu-id="6ca0a-108">[in] The ID of the interface implemented by the class.</span></span> <span data-ttu-id="6ca0a-109">インターフェイスが内部のみの場合、この値は NULL にすることがあります。</span><span class="sxs-lookup"><span data-stu-id="6ca0a-109">This value may be NULL if the interface is internal only.</span></span>  
  
 `pVTable`  
 <span data-ttu-id="6ca0a-110">[in]Vtable の先頭へのポインター。</span><span class="sxs-lookup"><span data-stu-id="6ca0a-110">[in] A pointer to the start of the vtable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ca0a-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="6ca0a-111">Remarks</span></span>  
 <span data-ttu-id="6ca0a-112">プロファイラーでは、スタックはガベージ コレクションを許可する状態にできない可能性がありますので、このメソッドの実装でブロックしないでくださいし、そのため、プリエンプティブなガベージ コレクションを有効にできません。</span><span class="sxs-lookup"><span data-stu-id="6ca0a-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="6ca0a-113">ここで、プロファイラーをブロックする場合とは、ガベージ コレクションが試行されると、ランタイムがこのコールバックが戻るまでブロックされます。</span><span class="sxs-lookup"><span data-stu-id="6ca0a-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="6ca0a-114">このメソッドのプロファイラーの実装には、任意の方法で管理されているメモリの割り当てが発生またはマネージ コードを呼び出さないでください。</span><span class="sxs-lookup"><span data-stu-id="6ca0a-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ca0a-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="6ca0a-115">Requirements</span></span>  
 <span data-ttu-id="6ca0a-116">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ca0a-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ca0a-117">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6ca0a-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6ca0a-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6ca0a-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6ca0a-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ca0a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ca0a-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="6ca0a-120">See also</span></span>
- [<span data-ttu-id="6ca0a-121">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6ca0a-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="6ca0a-122">COMClassicVTableCreated メソッド</span><span class="sxs-lookup"><span data-stu-id="6ca0a-122">COMClassicVTableCreated Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtablecreated-method.md)
