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
ms.openlocfilehash: 9048d314404859a4264621a5da91c43c525027f9
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868201"
---
# <a name="icorprofilerthreadenumclone-method"></a><span data-ttu-id="ad183-102">ICorProfilerThreadEnum::Clone メソッド</span><span class="sxs-lookup"><span data-stu-id="ad183-102">ICorProfilerThreadEnum::Clone Method</span></span>
<span data-ttu-id="ad183-103">この[ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md)インターフェイスのコピーへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="ad183-103">Gets an interface pointer to a copy of this [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad183-104">構文</span><span class="sxs-lookup"><span data-stu-id="ad183-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone (    [out] ICorProfilerThreadEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad183-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ad183-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="ad183-106">入出力インターフェイスポインターへのポインター。これにより、この[ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md)インターフェイスのコピーが参照されます。</span><span class="sxs-lookup"><span data-stu-id="ad183-106">[out] A pointer to the interface pointer, which, in turn, points to the copy of this [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) interface.</span></span> <span data-ttu-id="ad183-107">列挙子のコピーは、この列挙子とは別に独自の列挙状態を保持します。</span><span class="sxs-lookup"><span data-stu-id="ad183-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="ad183-108">ただし、コピーの最初のカーソル位置は、この列挙子の現在のカーソル位置と同じです。</span><span class="sxs-lookup"><span data-stu-id="ad183-108">However, the initial cursor position of the copy is the same as this current cursor position of the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad183-109">要件</span><span class="sxs-lookup"><span data-stu-id="ad183-109">Requirements</span></span>  
 <span data-ttu-id="ad183-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad183-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad183-111">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ad183-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ad183-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ad183-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ad183-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad183-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad183-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="ad183-114">See also</span></span>

- [<span data-ttu-id="ad183-115">ICorProfilerThreadEnum</span><span class="sxs-lookup"><span data-stu-id="ad183-115">ICorProfilerThreadEnum</span></span>](icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="ad183-116">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="ad183-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
