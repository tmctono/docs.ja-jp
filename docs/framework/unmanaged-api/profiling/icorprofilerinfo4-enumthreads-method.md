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
ms.openlocfilehash: d42c86a458661d3559f99235a6d5b208c82d1963
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502809"
---
# <a name="icorprofilerinfo4enumthreads-method"></a><span data-ttu-id="fdc24-102">ICorProfilerInfo4::EnumThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="fdc24-102">ICorProfilerInfo4::EnumThreads Method</span></span>
<span data-ttu-id="fdc24-103">プロファイリングされたプロセス内のすべてのマネージスレッドのコレクションを順番に反復処理するメソッドを提供する列挙子を返します。</span><span class="sxs-lookup"><span data-stu-id="fdc24-103">Returns an enumerator that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdc24-104">構文</span><span class="sxs-lookup"><span data-stu-id="fdc24-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumThreads([out]  
            ICorProfilerThreadEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fdc24-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fdc24-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="fdc24-106">入出力[ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md)インターフェイスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="fdc24-106">[out] A pointer to an [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fdc24-107">解説</span><span class="sxs-lookup"><span data-stu-id="fdc24-107">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fdc24-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="fdc24-108">Requirements</span></span>  
 <span data-ttu-id="fdc24-109">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fdc24-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fdc24-110">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fdc24-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fdc24-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fdc24-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fdc24-112">**.NET Framework のバージョン:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fdc24-112">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdc24-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="fdc24-113">See also</span></span>

- [<span data-ttu-id="fdc24-114">ICorProfilerThreadEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fdc24-114">ICorProfilerThreadEnum Interface</span></span>](icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="fdc24-115">ICorProfilerInfo4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fdc24-115">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="fdc24-116">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="fdc24-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="fdc24-117">プロファイル</span><span class="sxs-lookup"><span data-stu-id="fdc24-117">Profiling</span></span>](index.md)
