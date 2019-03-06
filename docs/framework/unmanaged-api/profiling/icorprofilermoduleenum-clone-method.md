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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fd3e3739ea9b5330f456156c0455009d90478649
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57470472"
---
# <a name="icorprofilermoduleenumclone-method"></a><span data-ttu-id="707ce-102">ICorProfilerModuleEnum::Clone メソッド</span><span class="sxs-lookup"><span data-stu-id="707ce-102">ICorProfilerModuleEnum::Clone Method</span></span>
<span data-ttu-id="707ce-103">このコピーにインターフェイス ポインターを取得[ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="707ce-103">Gets an interface pointer to a copy of this [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="707ce-104">構文</span><span class="sxs-lookup"><span data-stu-id="707ce-104">Syntax</span></span>  
  
```  
HRESULT Clone([out] ICorProfilerObjectEnum **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="707ce-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="707ce-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="707ce-106">[out]さらにこのコピーを指すインターフェイス ポインターへのポインター [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="707ce-106">[out] A pointer to the interface pointer that in turn points to the copy of this [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) interface.</span></span> <span data-ttu-id="707ce-107">列挙子のコピーでは、この列挙子から個別に独自の列挙状態を保持します。</span><span class="sxs-lookup"><span data-stu-id="707ce-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="707ce-108">ただし、コピーの初期のカーソル位置では、この列挙子の現在のカーソル位置の場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="707ce-108">However, the copy's initial cursor position is the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="707ce-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="707ce-109">Requirements</span></span>  
 <span data-ttu-id="707ce-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="707ce-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="707ce-111">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="707ce-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="707ce-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="707ce-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="707ce-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="707ce-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="707ce-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="707ce-114">See also</span></span>
- [<span data-ttu-id="707ce-115">ICorProfilerModuleEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="707ce-115">ICorProfilerModuleEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)
- [<span data-ttu-id="707ce-116">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="707ce-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
