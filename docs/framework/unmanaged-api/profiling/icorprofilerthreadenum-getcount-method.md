---
title: ICorProfilerThreadEnum::GetCount メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum.GetCount
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum::GetCount
helpviewer_keywords:
- ICorProfilerThreadEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerThreadEnum interface [.NET Framework profiling]
ms.assetid: d6dbdc4a-6115-455d-a3f3-704a81d3646b
topic_type:
- apiref
ms.openlocfilehash: 4bc2ea083d5278afc9278d388f57b048f7682ca6
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84494398"
---
# <a name="icorprofilerthreadenumgetcount-method"></a><span data-ttu-id="b19e0-102">ICorProfilerThreadEnum::GetCount メソッド</span><span class="sxs-lookup"><span data-stu-id="b19e0-102">ICorProfilerThreadEnum::GetCount Method</span></span>
<span data-ttu-id="b19e0-103">アプリケーションで使用されるスレッドの数を取得します。</span><span class="sxs-lookup"><span data-stu-id="b19e0-103">Gets the number of threads that are used by the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b19e0-104">構文</span><span class="sxs-lookup"><span data-stu-id="b19e0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (    [out] ULONG * pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b19e0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b19e0-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="b19e0-106">入出力アプリケーションによって使用されるスレッドの数。</span><span class="sxs-lookup"><span data-stu-id="b19e0-106">[out] The number of threads used by the application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b19e0-107">要件</span><span class="sxs-lookup"><span data-stu-id="b19e0-107">Requirements</span></span>  
 <span data-ttu-id="b19e0-108">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b19e0-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b19e0-109">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b19e0-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b19e0-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b19e0-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b19e0-111">**.NET Framework のバージョン:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b19e0-111">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b19e0-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="b19e0-112">See also</span></span>

- [<span data-ttu-id="b19e0-113">ICorProfilerThreadEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b19e0-113">ICorProfilerThreadEnum Interface</span></span>](icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="b19e0-114">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="b19e0-114">Profiling Interfaces</span></span>](profiling-interfaces.md)
