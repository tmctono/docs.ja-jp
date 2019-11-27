---
title: ICorProfilerCallback::ExceptionOSHandlerLeave メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionOSHandlerLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionOSHandlerLeave
helpviewer_keywords:
- ExceptionOSHandlerLeave method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionOSHandlerLeave method [.NET Framework profiling]
ms.assetid: 4d164676-0ee9-4f67-a8ea-cb474db09053
topic_type:
- apiref
ms.openlocfilehash: e54f87f5f02a1857fd9b7639d00d4bcb976665b1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445411"
---
# <a name="icorprofilercallbackexceptionoshandlerleave-method"></a><span data-ttu-id="0f660-102">ICorProfilerCallback::ExceptionOSHandlerLeave メソッド</span><span class="sxs-lookup"><span data-stu-id="0f660-102">ICorProfilerCallback::ExceptionOSHandlerLeave Method</span></span>
<span data-ttu-id="0f660-103">実装されていません。</span><span class="sxs-lookup"><span data-stu-id="0f660-103">Not implemented.</span></span> <span data-ttu-id="0f660-104">アンマネージ例外情報を必要とするプロファイラーは、他の方法でこの情報を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f660-104">A profiler that needs unmanaged exception information must obtain this information through other means.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f660-105">構文</span><span class="sxs-lookup"><span data-stu-id="0f660-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionOSHandlerLeave(  
    [in] UINT_PTR __unused);  
```  
  
## <a name="requirements"></a><span data-ttu-id="0f660-106">要件</span><span class="sxs-lookup"><span data-stu-id="0f660-106">Requirements</span></span>  
 <span data-ttu-id="0f660-107">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f660-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f660-108">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0f660-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0f660-109">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0f660-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0f660-110">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f660-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f660-111">参照</span><span class="sxs-lookup"><span data-stu-id="0f660-111">See also</span></span>

- [<span data-ttu-id="0f660-112">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0f660-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
