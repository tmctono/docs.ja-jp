---
title: ICorProfilerCallback::ExceptionCLRCatcherExecute メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionCLRCatcherExecute
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCLRCatcherExecute
helpviewer_keywords:
- ExceptionCLRCatcherExecute method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionCLRCatcherExecute method [.NET Framework profiling]
ms.assetid: aaac8f98-5cf4-42c7-b04b-556cce367e36
topic_type:
- apiref
ms.openlocfilehash: 165981627337c562dd3721b7d93cb2027d0a0c37
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444945"
---
# <a name="icorprofilercallbackexceptionclrcatcherexecute-method"></a><span data-ttu-id="496fd-102">ICorProfilerCallback::ExceptionCLRCatcherExecute メソッド</span><span class="sxs-lookup"><span data-stu-id="496fd-102">ICorProfilerCallback::ExceptionCLRCatcherExecute Method</span></span>
<span data-ttu-id="496fd-103">Called when a `catch` block for an exception is executed inside the common language runtime (CLR) itself.</span><span class="sxs-lookup"><span data-stu-id="496fd-103">Called when a `catch` block for an exception is executed inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="496fd-104">This method is obsolete in the .NET Framework version 2.0.</span><span class="sxs-lookup"><span data-stu-id="496fd-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="496fd-105">構文</span><span class="sxs-lookup"><span data-stu-id="496fd-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCLRCatcherExecute();  
```  
  
## <a name="requirements"></a><span data-ttu-id="496fd-106">［要件］</span><span class="sxs-lookup"><span data-stu-id="496fd-106">Requirements</span></span>  
 <span data-ttu-id="496fd-107">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="496fd-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="496fd-108">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="496fd-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="496fd-109">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="496fd-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="496fd-110">**.NET Framework Versions:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="496fd-110">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="496fd-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="496fd-111">See also</span></span>

- [<span data-ttu-id="496fd-112">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="496fd-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="496fd-113">ExceptionCLRCatcherFound メソッド</span><span class="sxs-lookup"><span data-stu-id="496fd-113">ExceptionCLRCatcherFound Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherfound-method.md)
