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
ms.openlocfilehash: be5d05c34272b9fa5755b4d0e22fa9094707c5ec
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61703557"
---
# <a name="icorprofilerinfo3enummodules-method"></a><span data-ttu-id="ed55c-102">ICorProfilerInfo3::EnumModules メソッド</span><span class="sxs-lookup"><span data-stu-id="ed55c-102">ICorProfilerInfo3::EnumModules Method</span></span>
<span data-ttu-id="ed55c-103">アプリケーションに読み込まれるマネージド モジュールのコレクションを順番に反復処理するメソッドを提供する列挙子を返します。</span><span class="sxs-lookup"><span data-stu-id="ed55c-103">Returns an enumerator that provides methods to sequentially iterate through a collection of managed modules that are loaded into the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed55c-104">構文</span><span class="sxs-lookup"><span data-stu-id="ed55c-104">Syntax</span></span>  
  
```  
HRESULT EnumModules([out] ICorProfilerModuleEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ed55c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ed55c-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="ed55c-106">[out]ポインター、 [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="ed55c-106">[out] A pointer to an [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ed55c-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="ed55c-107">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed55c-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="ed55c-108">Requirements</span></span>  
 <span data-ttu-id="ed55c-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed55c-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed55c-110">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ed55c-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ed55c-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ed55c-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ed55c-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed55c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed55c-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="ed55c-113">See also</span></span>

- [<span data-ttu-id="ed55c-114">ICorProfilerFunctionEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ed55c-114">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="ed55c-115">ICorProfilerInfo3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ed55c-115">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="ed55c-116">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="ed55c-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="ed55c-117">プロファイル</span><span class="sxs-lookup"><span data-stu-id="ed55c-117">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
