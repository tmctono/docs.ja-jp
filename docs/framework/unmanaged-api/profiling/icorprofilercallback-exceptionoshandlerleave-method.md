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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0decfde08a9097c8fe5185c8b5a3fef4f7f68189
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61598728"
---
# <a name="icorprofilercallbackexceptionoshandlerleave-method"></a><span data-ttu-id="d6b72-102">ICorProfilerCallback::ExceptionOSHandlerLeave メソッド</span><span class="sxs-lookup"><span data-stu-id="d6b72-102">ICorProfilerCallback::ExceptionOSHandlerLeave Method</span></span>
<span data-ttu-id="d6b72-103">実装されていません。</span><span class="sxs-lookup"><span data-stu-id="d6b72-103">Not implemented.</span></span> <span data-ttu-id="d6b72-104">非管理対象の例外情報を必要とするプロファイラーでは、他の手段では、この情報を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6b72-104">A profiler that needs unmanaged exception information must obtain this information through other means.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6b72-105">構文</span><span class="sxs-lookup"><span data-stu-id="d6b72-105">Syntax</span></span>  
  
```  
HRESULT ExceptionOSHandlerLeave(  
    [in] UINT_PTR __unused);  
```  
  
## <a name="requirements"></a><span data-ttu-id="d6b72-106">必要条件</span><span class="sxs-lookup"><span data-stu-id="d6b72-106">Requirements</span></span>  
 <span data-ttu-id="d6b72-107">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6b72-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6b72-108">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d6b72-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d6b72-109">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d6b72-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6b72-110">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6b72-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6b72-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="d6b72-111">See also</span></span>

- [<span data-ttu-id="d6b72-112">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d6b72-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
