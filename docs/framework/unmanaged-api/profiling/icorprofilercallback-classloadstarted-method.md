---
title: ICorProfilerCallback::ClassLoadStarted メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassLoadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassLoadStarted
helpviewer_keywords:
- ICorProfilerCallback::ClassLoadStarted method [.NET Framework profiling]
- ClassLoadStarted method [.NET Framework profiling]
ms.assetid: 9f728de8-45c2-45a5-ac4a-45660bd36ecf
topic_type:
- apiref
ms.openlocfilehash: 5b465216da39e8cf207f0614519720453c384ae9
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866586"
---
# <a name="icorprofilercallbackclassloadstarted-method"></a><span data-ttu-id="b97bc-102">ICorProfilerCallback::ClassLoadStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="b97bc-102">ICorProfilerCallback::ClassLoadStarted Method</span></span>
<span data-ttu-id="b97bc-103">クラスが読み込まれていることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="b97bc-103">Notifies the profiler that a class is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b97bc-104">構文</span><span class="sxs-lookup"><span data-stu-id="b97bc-104">Syntax</span></span>  
  
```cpp  
HRESULT ClassLoadStarted(  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b97bc-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b97bc-105">Parameters</span></span>

- `classId`

  <span data-ttu-id="b97bc-106">の \[] は、読み込むクラスを識別します。</span><span class="sxs-lookup"><span data-stu-id="b97bc-106">\[in] Identifies the class that is being loaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="b97bc-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="b97bc-107">Remarks</span></span>  
 <span data-ttu-id="b97bc-108">`classId` の値は、 [ICorProfilerCallback:: ClassLoadFinished](icorprofilercallback-classloadfinished-method.md)メソッドが呼び出されるまで、情報要求に対して無効です。</span><span class="sxs-lookup"><span data-stu-id="b97bc-108">The value of `classId` is not valid for an information request until the [ICorProfilerCallback::ClassLoadFinished](icorprofilercallback-classloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b97bc-109">要件</span><span class="sxs-lookup"><span data-stu-id="b97bc-109">Requirements</span></span>  
 <span data-ttu-id="b97bc-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b97bc-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b97bc-111">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b97bc-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b97bc-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b97bc-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b97bc-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b97bc-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b97bc-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="b97bc-114">See also</span></span>

- [<span data-ttu-id="b97bc-115">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b97bc-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
