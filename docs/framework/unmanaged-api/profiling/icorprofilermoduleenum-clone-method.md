---
title: ICorProfilerModuleEnum::Clone メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum.Clone Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum::Clone
helpviewer_keywords:
- Clone method, ICorProfilerModuleEnum interface [.NET Framework profiling]
- ICorProfilerModuleEnum::Clone method [.NET Framework profiling]
ms.assetid: 7dec7e36-8d88-416d-b437-abf98b76c1df
topic_type:
- apiref
ms.openlocfilehash: ccbb051ac30fb25199ce12c16fff74bb0b9944fa
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495087"
---
# <a name="icorprofilermoduleenumclone-method"></a><span data-ttu-id="5f6e8-102">ICorProfilerModuleEnum::Clone メソッド</span><span class="sxs-lookup"><span data-stu-id="5f6e8-102">ICorProfilerModuleEnum::Clone Method</span></span>
<span data-ttu-id="5f6e8-103">この[ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md)インターフェイスのコピーへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="5f6e8-103">Gets an interface pointer to a copy of this [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f6e8-104">構文</span><span class="sxs-lookup"><span data-stu-id="5f6e8-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone([out] ICorProfilerObjectEnum **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f6e8-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5f6e8-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="5f6e8-106">入出力次に、この[ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md)インターフェイスのコピーを指すインターフェイスポインターへのポインター。</span><span class="sxs-lookup"><span data-stu-id="5f6e8-106">[out] A pointer to the interface pointer that in turn points to the copy of this [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) interface.</span></span> <span data-ttu-id="5f6e8-107">列挙子のコピーは、この列挙子とは別に独自の列挙状態を保持します。</span><span class="sxs-lookup"><span data-stu-id="5f6e8-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="5f6e8-108">ただし、コピーの初期カーソル位置は、この列挙子の現在のカーソル位置と同じです。</span><span class="sxs-lookup"><span data-stu-id="5f6e8-108">However, the copy's initial cursor position is the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f6e8-109">要件</span><span class="sxs-lookup"><span data-stu-id="5f6e8-109">Requirements</span></span>  
 <span data-ttu-id="5f6e8-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5f6e8-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f6e8-111">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5f6e8-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5f6e8-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5f6e8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5f6e8-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f6e8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f6e8-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="5f6e8-114">See also</span></span>

- [<span data-ttu-id="5f6e8-115">ICorProfilerModuleEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5f6e8-115">ICorProfilerModuleEnum Interface</span></span>](icorprofilermoduleenum-interface.md)
- [<span data-ttu-id="5f6e8-116">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="5f6e8-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
