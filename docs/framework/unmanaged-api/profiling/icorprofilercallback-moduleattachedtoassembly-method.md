---
title: ICorProfilerCallback::ModuleAttachedToAssembly メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleAttachedToAssembly
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleAttachedToAssembly
helpviewer_keywords:
- ICorProfilerCallback::ModuleAttachedToAssembly method [.NET Framework profiling]
- ModuleAttachedToAssembly method [.NET Framework profiling]
ms.assetid: b595798a-5d40-4cac-ab4f-911c61d2c5d2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 791827b9c4b60cb2ee963881bc8e1a6131cd00fb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59139920"
---
# <a name="icorprofilercallbackmoduleattachedtoassembly-method"></a><span data-ttu-id="c0f0b-102">ICorProfilerCallback::ModuleAttachedToAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="c0f0b-102">ICorProfilerCallback::ModuleAttachedToAssembly Method</span></span>
<span data-ttu-id="c0f0b-103">モジュールが、親アセンブリに関連付けられていることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="c0f0b-103">Notifies the profiler that a module is being attached to its parent assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0f0b-104">構文</span><span class="sxs-lookup"><span data-stu-id="c0f0b-104">Syntax</span></span>  
  
```  
HRESULT ModuleAttachedToAssembly(  
    [in] ModuleID   moduleId,  
    [in] AssemblyID AssemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0f0b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c0f0b-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="c0f0b-106">[in]アタッチされるモジュールの ID。</span><span class="sxs-lookup"><span data-stu-id="c0f0b-106">[in] The ID of the module that is being attached.</span></span>  
  
 `AssemblyId`  
 <span data-ttu-id="c0f0b-107">[in]モジュールが接続されている親アセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="c0f0b-107">[in] The ID of the parent assembly to which the module is attached.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c0f0b-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="c0f0b-108">Remarks</span></span>  
 <span data-ttu-id="c0f0b-109">呼び出すことによってインポート アドレス テーブル (IAT) を通じて、モジュールを読み込むことが`LoadLibrary`、またはメタデータの参照を使用します。</span><span class="sxs-lookup"><span data-stu-id="c0f0b-109">A module can be loaded through an import address table (IAT), through a call to `LoadLibrary`, or through a metadata reference.</span></span> <span data-ttu-id="c0f0b-110">その結果、共通言語ランタイム (CLR) のローダーでは、モジュールが存在するアセンブリを決定するための複数のコード パスがあります。</span><span class="sxs-lookup"><span data-stu-id="c0f0b-110">As a result, the common language runtime (CLR) loader has multiple code paths for determining the assembly in which a module lives.</span></span> <span data-ttu-id="c0f0b-111">したがって、これは後に[icorprofilercallback::moduleloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)モジュールには、どのようなアセンブリがわからない、という内にあるし、親アセンブリの ID を取得することはできません。</span><span class="sxs-lookup"><span data-stu-id="c0f0b-111">Therefore, it is possible that after [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) is called, the module does not know what assembly it is in and getting the parent assembly ID is not possible.</span></span> <span data-ttu-id="c0f0b-112">`ModuleAttachedToAssembly`モジュールが、親アセンブリとその親アセンブリの ID を取得するアタッチされている場合、メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="c0f0b-112">The `ModuleAttachedToAssembly` method is called when the module is attached to its parent assembly and its parent assembly ID can be obtained.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0f0b-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="c0f0b-113">Requirements</span></span>  
 <span data-ttu-id="c0f0b-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0f0b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0f0b-115">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c0f0b-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c0f0b-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c0f0b-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="c0f0b-117">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="c0f0b-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c0f0b-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="c0f0b-118">See also</span></span>

- [<span data-ttu-id="c0f0b-119">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c0f0b-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
