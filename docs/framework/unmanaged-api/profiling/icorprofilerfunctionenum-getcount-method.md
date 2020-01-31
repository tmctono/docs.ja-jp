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
ms.openlocfilehash: 8a21f1c0018e99b94a1b9910b6f266bdca84b7fe
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864558"
---
# <a name="icorprofilerfunctionenumgetcount-method"></a><span data-ttu-id="625b9-102">ICorProfilerFunctionEnum::GetCount メソッド</span><span class="sxs-lookup"><span data-stu-id="625b9-102">ICorProfilerFunctionEnum::GetCount Method</span></span>
<span data-ttu-id="625b9-103">アプリケーションによって読み込まれたか、またはプロファイラーによって強制的に読み込まれた関数の数を取得します。</span><span class="sxs-lookup"><span data-stu-id="625b9-103">Gets the number of functions that were loaded by the application or forcibly loaded by the profiler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="625b9-104">構文</span><span class="sxs-lookup"><span data-stu-id="625b9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount([out] ULONG * pcelt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="625b9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="625b9-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="625b9-106">入出力読み込まれた関数の数。</span><span class="sxs-lookup"><span data-stu-id="625b9-106">[out] The number of functions that were loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="625b9-107">要件</span><span class="sxs-lookup"><span data-stu-id="625b9-107">Requirements</span></span>  
 <span data-ttu-id="625b9-108">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="625b9-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="625b9-109">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="625b9-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="625b9-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="625b9-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="625b9-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="625b9-111">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="625b9-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="625b9-112">See also</span></span>

- [<span data-ttu-id="625b9-113">ICorProfilerFunctionEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="625b9-113">ICorProfilerFunctionEnum Interface</span></span>](icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="625b9-114">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="625b9-114">Profiling Interfaces</span></span>](profiling-interfaces.md)
