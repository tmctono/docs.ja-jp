---
title: ICorProfilerInfo3::EnumModules メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.EnumModules Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::EnumModules
helpviewer_keywords:
- ICorProfilerInfo3::EnumModules method [.NET Framework profiling]
- EnumModules method [.NET Framework profiling]
ms.assetid: 1bf00b42-69da-4019-91b3-bf88026e83fb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 73218a5b63ae53ac125d3d807c1a50bdbf0d9c8a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57503061"
---
# <a name="icorprofilerinfo3enummodules-method"></a><span data-ttu-id="5ab4e-102">ICorProfilerInfo3::EnumModules メソッド</span><span class="sxs-lookup"><span data-stu-id="5ab4e-102">ICorProfilerInfo3::EnumModules Method</span></span>
<span data-ttu-id="5ab4e-103">アプリケーションに読み込まれるマネージド モジュールのコレクションを順番に反復処理するメソッドを提供する列挙子を返します。</span><span class="sxs-lookup"><span data-stu-id="5ab4e-103">Returns an enumerator that provides methods to sequentially iterate through a collection of managed modules that are loaded into the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ab4e-104">構文</span><span class="sxs-lookup"><span data-stu-id="5ab4e-104">Syntax</span></span>  
  
```  
HRESULT EnumModules([out] ICorProfilerModuleEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ab4e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5ab4e-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="5ab4e-106">[out]ポインター、 [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="5ab4e-106">[out] A pointer to an [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ab4e-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="5ab4e-107">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ab4e-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="5ab4e-108">Requirements</span></span>  
 <span data-ttu-id="5ab4e-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ab4e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ab4e-110">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5ab4e-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5ab4e-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5ab4e-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5ab4e-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ab4e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ab4e-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="5ab4e-113">See also</span></span>
- [<span data-ttu-id="5ab4e-114">ICorProfilerFunctionEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5ab4e-114">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="5ab4e-115">ICorProfilerInfo3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5ab4e-115">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="5ab4e-116">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="5ab4e-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="5ab4e-117">プロファイル</span><span class="sxs-lookup"><span data-stu-id="5ab4e-117">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
