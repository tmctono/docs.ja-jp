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
ms.openlocfilehash: 6827a61f670c07595ac78bcd4a8aef201a48b1e0
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479143"
---
# <a name="icorprofilerfunctionenumgetcount-method"></a><span data-ttu-id="b7612-102">ICorProfilerFunctionEnum::GetCount メソッド</span><span class="sxs-lookup"><span data-stu-id="b7612-102">ICorProfilerFunctionEnum::GetCount Method</span></span>
<span data-ttu-id="b7612-103">アプリケーションによって読み込まれたか、またはプロファイラーによって強制的に読み込まれた関数の数を取得します。</span><span class="sxs-lookup"><span data-stu-id="b7612-103">Gets the number of functions that were loaded by the application or forcibly loaded by the profiler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7612-104">構文</span><span class="sxs-lookup"><span data-stu-id="b7612-104">Syntax</span></span>  
  
```  
HRESULT GetCount([out] ULONG * pcelt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b7612-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b7612-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="b7612-106">[out]読み込まれた関数の数。</span><span class="sxs-lookup"><span data-stu-id="b7612-106">[out] The number of functions that were loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7612-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="b7612-107">Requirements</span></span>  
 <span data-ttu-id="b7612-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7612-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7612-109">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b7612-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b7612-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7612-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7612-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7612-111">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7612-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="b7612-112">See also</span></span>
- [<span data-ttu-id="b7612-113">ICorProfilerFunctionEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b7612-113">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="b7612-114">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="b7612-114">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
