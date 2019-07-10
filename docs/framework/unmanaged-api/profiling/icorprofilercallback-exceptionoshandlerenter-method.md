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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d9167b35556fafb33e61e1dc050488aec2b7fa01
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776018"
---
# <a name="icorprofilercallbackexceptionoshandlerenter-method"></a><span data-ttu-id="71079-102">ICorProfilerCallback::ExceptionOSHandlerEnter メソッド</span><span class="sxs-lookup"><span data-stu-id="71079-102">ICorProfilerCallback::ExceptionOSHandlerEnter Method</span></span>
<span data-ttu-id="71079-103">実装されていません。</span><span class="sxs-lookup"><span data-stu-id="71079-103">Not implemented.</span></span> <span data-ttu-id="71079-104">非管理対象の例外情報を必要とするプロファイラーでは、他の手段では、この情報を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="71079-104">A profiler that needs unmanaged exception information must obtain this information through other means.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71079-105">構文</span><span class="sxs-lookup"><span data-stu-id="71079-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionOSHandlerEnter(  
    [in] UINT_PTR __unused);  
```  
  
## <a name="requirements"></a><span data-ttu-id="71079-106">必要条件</span><span class="sxs-lookup"><span data-stu-id="71079-106">Requirements</span></span>  
 <span data-ttu-id="71079-107">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="71079-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71079-108">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="71079-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="71079-109">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="71079-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="71079-110">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71079-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71079-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="71079-111">See also</span></span>

- [<span data-ttu-id="71079-112">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="71079-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
