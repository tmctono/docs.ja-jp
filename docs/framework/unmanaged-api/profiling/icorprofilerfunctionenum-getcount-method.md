---
title: ICorProfilerFunctionEnum::GetCount メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum.GetCount Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum::GetCount
helpviewer_keywords:
- ICorProfilerFunctionEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 62ec65e3-3e9d-400b-ae61-d24b8963995b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6403540f9641ce885edf2760370e35f48faf1f10
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780319"
---
# <a name="icorprofilerfunctionenumgetcount-method"></a><span data-ttu-id="c7082-102">ICorProfilerFunctionEnum::GetCount メソッド</span><span class="sxs-lookup"><span data-stu-id="c7082-102">ICorProfilerFunctionEnum::GetCount Method</span></span>
<span data-ttu-id="c7082-103">アプリケーションによって読み込まれたか、またはプロファイラーによって強制的に読み込まれた関数の数を取得します。</span><span class="sxs-lookup"><span data-stu-id="c7082-103">Gets the number of functions that were loaded by the application or forcibly loaded by the profiler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7082-104">構文</span><span class="sxs-lookup"><span data-stu-id="c7082-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount([out] ULONG * pcelt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7082-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c7082-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="c7082-106">[out]読み込まれた関数の数。</span><span class="sxs-lookup"><span data-stu-id="c7082-106">[out] The number of functions that were loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7082-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="c7082-107">Requirements</span></span>  
 <span data-ttu-id="c7082-108">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7082-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7082-109">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c7082-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c7082-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c7082-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c7082-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7082-111">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7082-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="c7082-112">See also</span></span>

- [<span data-ttu-id="c7082-113">ICorProfilerFunctionEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c7082-113">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="c7082-114">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="c7082-114">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
