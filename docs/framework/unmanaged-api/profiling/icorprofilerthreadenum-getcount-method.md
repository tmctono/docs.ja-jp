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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fbdb9f6fc8376e080455957367dc79f4dfed8843
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781196"
---
# <a name="icorprofilerthreadenumgetcount-method"></a><span data-ttu-id="f923a-102">ICorProfilerThreadEnum::GetCount メソッド</span><span class="sxs-lookup"><span data-stu-id="f923a-102">ICorProfilerThreadEnum::GetCount Method</span></span>
<span data-ttu-id="f923a-103">アプリケーションで使用されるスレッドの数を取得します。</span><span class="sxs-lookup"><span data-stu-id="f923a-103">Gets the number of threads that are used by the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f923a-104">構文</span><span class="sxs-lookup"><span data-stu-id="f923a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (    [out] ULONG * pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f923a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f923a-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="f923a-106">[out]アプリケーションで使用されるスレッドの数。</span><span class="sxs-lookup"><span data-stu-id="f923a-106">[out] The number of threads used by the application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f923a-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="f923a-107">Requirements</span></span>  
 <span data-ttu-id="f923a-108">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f923a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f923a-109">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f923a-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f923a-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f923a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f923a-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f923a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f923a-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="f923a-112">See also</span></span>

- [<span data-ttu-id="f923a-113">ICorProfilerThreadEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f923a-113">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="f923a-114">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="f923a-114">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
