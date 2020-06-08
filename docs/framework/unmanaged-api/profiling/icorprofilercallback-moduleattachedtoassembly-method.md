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
ms.openlocfilehash: 4f494919d11e0f979cf1964c08106fbb9b9ed20b
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503394"
---
# <a name="icorprofilercallbackmoduleattachedtoassembly-method"></a><span data-ttu-id="042f8-102">ICorProfilerCallback::ModuleAttachedToAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="042f8-102">ICorProfilerCallback::ModuleAttachedToAssembly Method</span></span>
<span data-ttu-id="042f8-103">モジュールが親アセンブリにアタッチされていることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="042f8-103">Notifies the profiler that a module is being attached to its parent assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="042f8-104">構文</span><span class="sxs-lookup"><span data-stu-id="042f8-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleAttachedToAssembly(  
    [in] ModuleID   moduleId,  
    [in] AssemblyID AssemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="042f8-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="042f8-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="042f8-106">からアタッチされているモジュールの ID。</span><span class="sxs-lookup"><span data-stu-id="042f8-106">[in] The ID of the module that is being attached.</span></span>  
  
 `AssemblyId`  
 <span data-ttu-id="042f8-107">からモジュールがアタッチされている親アセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="042f8-107">[in] The ID of the parent assembly to which the module is attached.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="042f8-108">解説</span><span class="sxs-lookup"><span data-stu-id="042f8-108">Remarks</span></span>  
 <span data-ttu-id="042f8-109">モジュールは、インポートアドレステーブル (IAT)、の呼び出し、 `LoadLibrary` またはメタデータ参照を使用して読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="042f8-109">A module can be loaded through an import address table (IAT), through a call to `LoadLibrary`, or through a metadata reference.</span></span> <span data-ttu-id="042f8-110">その結果、共通言語ランタイム (CLR) ローダーには、モジュールが存在するアセンブリを決定するための複数のコードパスがあります。</span><span class="sxs-lookup"><span data-stu-id="042f8-110">As a result, the common language runtime (CLR) loader has multiple code paths for determining the assembly in which a module lives.</span></span> <span data-ttu-id="042f8-111">したがって、 [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md)が呼び出された後、モジュールは、そのアセンブリを認識し、親アセンブリ ID を取得できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="042f8-111">Therefore, it is possible that after [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) is called, the module does not know what assembly it is in and getting the parent assembly ID is not possible.</span></span> <span data-ttu-id="042f8-112">この `ModuleAttachedToAssembly` メソッドは、モジュールが親アセンブリにアタッチされ、その親アセンブリ ID を取得できる場合に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="042f8-112">The `ModuleAttachedToAssembly` method is called when the module is attached to its parent assembly and its parent assembly ID can be obtained.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="042f8-113">要件</span><span class="sxs-lookup"><span data-stu-id="042f8-113">Requirements</span></span>  
 <span data-ttu-id="042f8-114">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="042f8-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="042f8-115">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="042f8-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="042f8-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="042f8-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="042f8-117">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="042f8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="042f8-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="042f8-118">See also</span></span>

- [<span data-ttu-id="042f8-119">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="042f8-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
