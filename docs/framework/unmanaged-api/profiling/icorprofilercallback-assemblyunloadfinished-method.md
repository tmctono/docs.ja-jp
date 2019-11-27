---
title: ICorProfilerCallback::AssemblyUnloadFinished メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyUnloadFinished
helpviewer_keywords:
- AssemblyUnloadFinished method [.NET Framework profiling]
- ICorProfilerCallback::AssemblyUnloadFinished method [.NET Framework profiling]
ms.assetid: 53fca564-84b1-44d4-9e21-17a492d2aae7
topic_type:
- apiref
ms.openlocfilehash: 01404d23707be90b6b15cf741632400d49f164de
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445152"
---
# <a name="icorprofilercallbackassemblyunloadfinished-method"></a><span data-ttu-id="93991-102">ICorProfilerCallback::AssemblyUnloadFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="93991-102">ICorProfilerCallback::AssemblyUnloadFinished Method</span></span>
<span data-ttu-id="93991-103">アセンブリがアンロードされたことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="93991-103">Notifies the profiler that an assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93991-104">構文</span><span class="sxs-lookup"><span data-stu-id="93991-104">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyUnloadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="93991-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="93991-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="93991-106">からアンロードされるアセンブリを識別します。</span><span class="sxs-lookup"><span data-stu-id="93991-106">[in] Identifies the assembly that is being unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="93991-107">からアセンブリが正常にアンロードされたかどうかを示す HRESULT。</span><span class="sxs-lookup"><span data-stu-id="93991-107">[in] An HRESULT that indicates whether the assembly was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="93991-108">コメント</span><span class="sxs-lookup"><span data-stu-id="93991-108">Remarks</span></span>  
 <span data-ttu-id="93991-109">`assemblyId` の値は、 [ICorProfilerCallback:: AssemblyUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md)メソッドが返された後の情報要求に対して無効です。</span><span class="sxs-lookup"><span data-stu-id="93991-109">The value of `assemblyId` is not valid for an information request after the [ICorProfilerCallback::AssemblyUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="93991-110">`AssemblyUnloadFinished` コールバックの後も、アセンブリのアンロードの一部が続行される場合があります。</span><span class="sxs-lookup"><span data-stu-id="93991-110">Some parts of unloading the assembly might continue after the `AssemblyUnloadFinished` callback.</span></span> <span data-ttu-id="93991-111">`hrStatus` のエラー HRESULT はエラーを示します。</span><span class="sxs-lookup"><span data-stu-id="93991-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="93991-112">ただし、`hrStatus` の成功 HRESULT は、アセンブリのアンロードの最初の部分が成功したことのみを示します。</span><span class="sxs-lookup"><span data-stu-id="93991-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93991-113">要件</span><span class="sxs-lookup"><span data-stu-id="93991-113">Requirements</span></span>  
 <span data-ttu-id="93991-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="93991-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93991-115">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="93991-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="93991-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="93991-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="93991-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93991-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93991-118">参照</span><span class="sxs-lookup"><span data-stu-id="93991-118">See also</span></span>

- [<span data-ttu-id="93991-119">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="93991-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
