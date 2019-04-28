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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a96a2a0d6e4bc48a46850aeaadd17c2669419cef
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61597453"
---
# <a name="icorprofilercallbackassemblyloadstarted-method"></a><span data-ttu-id="cd9ce-102">ICorProfilerCallback::AssemblyLoadStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="cd9ce-102">ICorProfilerCallback::AssemblyLoadStarted Method</span></span>
<span data-ttu-id="cd9ce-103">アセンブリが読み込まれていることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="cd9ce-103">Notifies the profiler that an assembly is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd9ce-104">構文</span><span class="sxs-lookup"><span data-stu-id="cd9ce-104">Syntax</span></span>  
  
```  
HRESULT AssemblyLoadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd9ce-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cd9ce-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="cd9ce-106">[in]読み込まれているアセンブリを識別します。</span><span class="sxs-lookup"><span data-stu-id="cd9ce-106">[in] Identifies the assembly that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cd9ce-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="cd9ce-107">Remarks</span></span>  
 <span data-ttu-id="cd9ce-108">値`assemblyId`まで情報の要求に対して無効です、 [icorprofilercallback::assemblyloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadfinished-method.md)メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="cd9ce-108">The value of `assemblyId` is not valid for an information request until the [ICorProfilerCallback::AssemblyLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd9ce-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="cd9ce-109">Requirements</span></span>  
 <span data-ttu-id="cd9ce-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd9ce-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd9ce-111">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cd9ce-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cd9ce-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cd9ce-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cd9ce-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd9ce-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd9ce-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="cd9ce-114">See also</span></span>

- [<span data-ttu-id="cd9ce-115">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cd9ce-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
