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
ms.openlocfilehash: 626ecddae8ba91d1830d98210208f9fbee36f073
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868588"
---
# <a name="icorprofilerinfo3enummodules-method"></a><span data-ttu-id="4a6f4-102">ICorProfilerInfo3::EnumModules メソッド</span><span class="sxs-lookup"><span data-stu-id="4a6f4-102">ICorProfilerInfo3::EnumModules Method</span></span>
<span data-ttu-id="4a6f4-103">アプリケーションに読み込まれるマネージド モジュールのコレクションを順番に反復処理するメソッドを提供する列挙子を返します。</span><span class="sxs-lookup"><span data-stu-id="4a6f4-103">Returns an enumerator that provides methods to sequentially iterate through a collection of managed modules that are loaded into the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a6f4-104">構文</span><span class="sxs-lookup"><span data-stu-id="4a6f4-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumModules([out] ICorProfilerModuleEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a6f4-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4a6f4-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="4a6f4-106">入出力[ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md)インターフェイスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="4a6f4-106">[out] A pointer to an [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4a6f4-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="4a6f4-107">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a6f4-108">要件</span><span class="sxs-lookup"><span data-stu-id="4a6f4-108">Requirements</span></span>  
 <span data-ttu-id="4a6f4-109">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a6f4-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a6f4-110">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4a6f4-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4a6f4-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4a6f4-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4a6f4-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a6f4-112">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a6f4-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="4a6f4-113">See also</span></span>

- [<span data-ttu-id="4a6f4-114">ICorProfilerFunctionEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4a6f4-114">ICorProfilerFunctionEnum Interface</span></span>](icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="4a6f4-115">ICorProfilerInfo3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4a6f4-115">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="4a6f4-116">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="4a6f4-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="4a6f4-117">プロファイル</span><span class="sxs-lookup"><span data-stu-id="4a6f4-117">Profiling</span></span>](index.md)
