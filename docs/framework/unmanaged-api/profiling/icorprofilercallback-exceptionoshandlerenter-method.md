---
title: ICorProfilerCallback::ExceptionOSHandlerEnter メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionOSHandlerEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionOSHandlerEnter
helpviewer_keywords:
- ExceptionOSHandlerEnter method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionOSHandlerEnter method [.NET Framework profiling]
ms.assetid: 09238b9b-9359-4780-89dc-2f5e4f57920e
topic_type:
- apiref
ms.openlocfilehash: c2c9ed848984d36ddf10d32d120deda76a4d47cc
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500287"
---
# <a name="icorprofilercallbackexceptionoshandlerenter-method"></a><span data-ttu-id="d8d4b-102">ICorProfilerCallback::ExceptionOSHandlerEnter メソッド</span><span class="sxs-lookup"><span data-stu-id="d8d4b-102">ICorProfilerCallback::ExceptionOSHandlerEnter Method</span></span>
<span data-ttu-id="d8d4b-103">実装されていません。</span><span class="sxs-lookup"><span data-stu-id="d8d4b-103">Not implemented.</span></span> <span data-ttu-id="d8d4b-104">アンマネージ例外情報を必要とするプロファイラーは、他の方法でこの情報を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8d4b-104">A profiler that needs unmanaged exception information must obtain this information through other means.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8d4b-105">構文</span><span class="sxs-lookup"><span data-stu-id="d8d4b-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionOSHandlerEnter(  
    [in] UINT_PTR __unused);  
```  
  
## <a name="requirements"></a><span data-ttu-id="d8d4b-106">要件</span><span class="sxs-lookup"><span data-stu-id="d8d4b-106">Requirements</span></span>  
 <span data-ttu-id="d8d4b-107">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8d4b-107">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8d4b-108">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d8d4b-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d8d4b-109">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d8d4b-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d8d4b-110">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8d4b-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8d4b-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="d8d4b-111">See also</span></span>

- [<span data-ttu-id="d8d4b-112">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d8d4b-112">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
