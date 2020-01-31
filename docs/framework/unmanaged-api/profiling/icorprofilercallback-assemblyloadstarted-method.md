---
title: ICorProfilerCallback::AssemblyLoadStarted メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyLoadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyLoadStarted
helpviewer_keywords:
- ICorProfilerCallback::AssemblyLoadStarted method [.NET Framework profiling]
- AssemblyLoadStarted method [.NET Framework profiling]
ms.assetid: 67e8209d-a0ca-4118-a6e6-c1ee0abc2221
topic_type:
- apiref
ms.openlocfilehash: 9899ea8afc739207ad0b70e9720e90e5c7f09fcf
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790190"
---
# <a name="icorprofilercallbackassemblyloadstarted-method"></a><span data-ttu-id="22f4c-102">ICorProfilerCallback::AssemblyLoadStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="22f4c-102">ICorProfilerCallback::AssemblyLoadStarted Method</span></span>
<span data-ttu-id="22f4c-103">アセンブリが読み込まれていることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="22f4c-103">Notifies the profiler that an assembly is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22f4c-104">構文</span><span class="sxs-lookup"><span data-stu-id="22f4c-104">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyLoadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="22f4c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="22f4c-105">Parameters</span></span>

- `assemblyId`

  <span data-ttu-id="22f4c-106">の \[] は、読み込むアセンブリを識別します。</span><span class="sxs-lookup"><span data-stu-id="22f4c-106">\[in] Identifies the assembly that is being loaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="22f4c-107">コメント</span><span class="sxs-lookup"><span data-stu-id="22f4c-107">Remarks</span></span>  
 <span data-ttu-id="22f4c-108">`assemblyId` の値は、 [ICorProfilerCallback:: AssemblyLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadfinished-method.md)メソッドが呼び出されるまで、情報要求に対して無効です。</span><span class="sxs-lookup"><span data-stu-id="22f4c-108">The value of `assemblyId` is not valid for an information request until the [ICorProfilerCallback::AssemblyLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22f4c-109">要件</span><span class="sxs-lookup"><span data-stu-id="22f4c-109">Requirements</span></span>  
 <span data-ttu-id="22f4c-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22f4c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22f4c-111">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="22f4c-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="22f4c-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="22f4c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="22f4c-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22f4c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22f4c-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="22f4c-114">See also</span></span>

- [<span data-ttu-id="22f4c-115">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="22f4c-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
