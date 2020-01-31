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
ms.openlocfilehash: dcb2af2507306b22da14c13a42e4019261c8fa8c
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866443"
---
# <a name="icorprofilercallbackexceptionoshandlerleave-method"></a><span data-ttu-id="47fad-102">ICorProfilerCallback::ExceptionOSHandlerLeave メソッド</span><span class="sxs-lookup"><span data-stu-id="47fad-102">ICorProfilerCallback::ExceptionOSHandlerLeave Method</span></span>
<span data-ttu-id="47fad-103">実装されていません。</span><span class="sxs-lookup"><span data-stu-id="47fad-103">Not implemented.</span></span> <span data-ttu-id="47fad-104">アンマネージ例外情報を必要とするプロファイラーは、他の方法でこの情報を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47fad-104">A profiler that needs unmanaged exception information must obtain this information through other means.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47fad-105">構文</span><span class="sxs-lookup"><span data-stu-id="47fad-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionOSHandlerLeave(  
    [in] UINT_PTR __unused);  
```  
  
## <a name="requirements"></a><span data-ttu-id="47fad-106">要件</span><span class="sxs-lookup"><span data-stu-id="47fad-106">Requirements</span></span>  
 <span data-ttu-id="47fad-107">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47fad-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47fad-108">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="47fad-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="47fad-109">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="47fad-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="47fad-110">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47fad-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47fad-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="47fad-111">See also</span></span>

- [<span data-ttu-id="47fad-112">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="47fad-112">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
