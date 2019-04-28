---
title: ICorProfilerThreadEnum::Clone メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum.Clone
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum::Clone
helpviewer_keywords:
- Clone method, ICorProfilerThreadEnum interface [.NET Framework profiling]
- ICorProfilerThreadEnum::Clone method [.NET Framework profiling]
ms.assetid: 5a278bc9-88e2-4c69-b035-9d550dd77081
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0301334621a2e393a59e7cc34f2964450a81213f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61597042"
---
# <a name="icorprofilerthreadenumclone-method"></a><span data-ttu-id="6c0a4-102">ICorProfilerThreadEnum::Clone メソッド</span><span class="sxs-lookup"><span data-stu-id="6c0a4-102">ICorProfilerThreadEnum::Clone Method</span></span>
<span data-ttu-id="6c0a4-103">このコピーにインターフェイス ポインターを取得[ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="6c0a4-103">Gets an interface pointer to a copy of this [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c0a4-104">構文</span><span class="sxs-lookup"><span data-stu-id="6c0a4-104">Syntax</span></span>  
  
```  
HRESULT Clone (    [out] ICorProfilerThreadEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c0a4-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6c0a4-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="6c0a4-106">[out]さらに、このコピーを指しますインターフェイス ポインターへのポインター [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="6c0a4-106">[out] A pointer to the interface pointer, which, in turn, points to the copy of this [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interface.</span></span> <span data-ttu-id="6c0a4-107">列挙子のコピーでは、この列挙子から個別に独自の列挙状態を保持します。</span><span class="sxs-lookup"><span data-stu-id="6c0a4-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="6c0a4-108">ただし、コピーの最初のカーソル位置では、この列挙子の現在のカーソル位置の場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="6c0a4-108">However, the initial cursor position of the copy is the same as this current cursor position of the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c0a4-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="6c0a4-109">Requirements</span></span>  
 <span data-ttu-id="6c0a4-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c0a4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c0a4-111">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6c0a4-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6c0a4-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6c0a4-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6c0a4-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c0a4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c0a4-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="6c0a4-114">See also</span></span>

- [<span data-ttu-id="6c0a4-115">ICorProfilerThreadEnum</span><span class="sxs-lookup"><span data-stu-id="6c0a4-115">ICorProfilerThreadEnum</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="6c0a4-116">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="6c0a4-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
