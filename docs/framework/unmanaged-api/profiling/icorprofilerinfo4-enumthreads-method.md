---
title: ICorProfilerInfo4::EnumThreads メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.EnumThreads
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::EnumThreads
helpviewer_keywords:
- ICorProfilerInfo4::EnumThreads method [.NET Framework profiling]
- EnumThreads method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: bca7a5b4-c207-4894-918c-0733926296dd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3d4cffc7c407db6acd15462e1e00769101e44b40
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780865"
---
# <a name="icorprofilerinfo4enumthreads-method"></a><span data-ttu-id="87b63-102">ICorProfilerInfo4::EnumThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="87b63-102">ICorProfilerInfo4::EnumThreads Method</span></span>
<span data-ttu-id="87b63-103">プロファイリングされたプロセスのすべてのマネージ スレッドのコレクションを順番に反復処理するメソッドを提供する列挙子を返します。</span><span class="sxs-lookup"><span data-stu-id="87b63-103">Returns an enumerator that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87b63-104">構文</span><span class="sxs-lookup"><span data-stu-id="87b63-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumThreads([out]  
            ICorProfilerThreadEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="87b63-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="87b63-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="87b63-106">[out]ポインター、 [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="87b63-106">[out] A pointer to an [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="87b63-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="87b63-107">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87b63-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="87b63-108">Requirements</span></span>  
 <span data-ttu-id="87b63-109">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="87b63-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87b63-110">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="87b63-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="87b63-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="87b63-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="87b63-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87b63-112">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87b63-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="87b63-113">See also</span></span>

- [<span data-ttu-id="87b63-114">ICorProfilerThreadEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="87b63-114">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="87b63-115">ICorProfilerInfo4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="87b63-115">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="87b63-116">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="87b63-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="87b63-117">プロファイル</span><span class="sxs-lookup"><span data-stu-id="87b63-117">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
