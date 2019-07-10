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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a75d31f0a2c844895363bb4693dbcb5aba4cce1f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67775510"
---
# <a name="icorprofilercallbackassemblyunloadfinished-method"></a><span data-ttu-id="a1ec0-102">ICorProfilerCallback::AssemblyUnloadFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="a1ec0-102">ICorProfilerCallback::AssemblyUnloadFinished Method</span></span>
<span data-ttu-id="a1ec0-103">アセンブリがアンロードされたことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="a1ec0-103">Notifies the profiler that an assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1ec0-104">構文</span><span class="sxs-lookup"><span data-stu-id="a1ec0-104">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyUnloadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1ec0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a1ec0-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="a1ec0-106">[in]アンロードされているアセンブリを識別します。</span><span class="sxs-lookup"><span data-stu-id="a1ec0-106">[in] Identifies the assembly that is being unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="a1ec0-107">[in]かどうか、アセンブリがアンロードされた正常を示す HRESULT。</span><span class="sxs-lookup"><span data-stu-id="a1ec0-107">[in] An HRESULT that indicates whether the assembly was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a1ec0-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="a1ec0-108">Remarks</span></span>  
 <span data-ttu-id="a1ec0-109">値`assemblyId`は後の情報の要求は無効です、 [icorprofilercallback::assemblyunloadstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md)メソッドを返します。</span><span class="sxs-lookup"><span data-stu-id="a1ec0-109">The value of `assemblyId` is not valid for an information request after the [ICorProfilerCallback::AssemblyUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="a1ec0-110">アセンブリのアンロードの一部が後に続ける可能性があります、`AssemblyUnloadFinished`コールバック。</span><span class="sxs-lookup"><span data-stu-id="a1ec0-110">Some parts of unloading the assembly might continue after the `AssemblyUnloadFinished` callback.</span></span> <span data-ttu-id="a1ec0-111">エラーの HRESULT で`hrStatus`失敗を示します。</span><span class="sxs-lookup"><span data-stu-id="a1ec0-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="a1ec0-112">ただし、成功 HRESULT で`hrStatus`のみのアセンブリのアンロードの最初の部分が成功したことを示します。</span><span class="sxs-lookup"><span data-stu-id="a1ec0-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1ec0-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="a1ec0-113">Requirements</span></span>  
 <span data-ttu-id="a1ec0-114">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1ec0-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1ec0-115">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a1ec0-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a1ec0-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a1ec0-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a1ec0-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1ec0-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1ec0-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="a1ec0-118">See also</span></span>

- [<span data-ttu-id="a1ec0-119">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a1ec0-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
