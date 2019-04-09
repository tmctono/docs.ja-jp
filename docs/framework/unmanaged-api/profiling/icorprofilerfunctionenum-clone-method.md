---
title: ICorProfilerFunctionEnum::Clone メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum.Clone Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum::Clone
helpviewer_keywords:
- ICorProfilerFunctionEnum::Clone method [.NET Framework profiling]
- Clone method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 0c3d4835-e111-4e82-af6d-53f140b8f2c9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5ffd1fcc36f0c6cc3c5f063c5a916e8918839566
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59135591"
---
# <a name="icorprofilerfunctionenumclone-method"></a><span data-ttu-id="1a0b1-102">ICorProfilerFunctionEnum::Clone メソッド</span><span class="sxs-lookup"><span data-stu-id="1a0b1-102">ICorProfilerFunctionEnum::Clone Method</span></span>
<span data-ttu-id="1a0b1-103">このコピーにインターフェイス ポインターを取得[ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="1a0b1-103">Gets an interface pointer to a copy of this [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a0b1-104">構文</span><span class="sxs-lookup"><span data-stu-id="1a0b1-104">Syntax</span></span>  
  
```  
HRESULT Clone([out] ICorProfilerFunctionEnum **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1a0b1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1a0b1-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="1a0b1-106">[out]さらに、このコピーを指しますインターフェイス ポインターへのポインター [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="1a0b1-106">[out] A pointer to the interface pointer, which, in turn, points to the copy of this [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) interface.</span></span> <span data-ttu-id="1a0b1-107">列挙子のコピーでは、この列挙子から個別に独自の列挙状態を保持します。</span><span class="sxs-lookup"><span data-stu-id="1a0b1-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="1a0b1-108">ただし、コピーの初期のカーソル位置では、この列挙子の現在のカーソル位置の場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="1a0b1-108">However, the copy's initial cursor position is the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a0b1-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="1a0b1-109">Requirements</span></span>  
 <span data-ttu-id="1a0b1-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a0b1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a0b1-111">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1a0b1-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1a0b1-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1a0b1-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="1a0b1-113">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="1a0b1-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1a0b1-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="1a0b1-114">See also</span></span>

- [<span data-ttu-id="1a0b1-115">ICorProfilerFunctionEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1a0b1-115">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="1a0b1-116">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="1a0b1-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
