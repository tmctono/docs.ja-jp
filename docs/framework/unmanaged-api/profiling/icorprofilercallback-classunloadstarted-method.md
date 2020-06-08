---
title: ICorProfilerCallback::ClassUnloadStarted メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassUnloadStarted
helpviewer_keywords:
- ClassUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ClassUnloadStarted method [.NET Framework profiling]
ms.assetid: bc93bead-f3a9-415c-b919-ddd3ca80facc
topic_type:
- apiref
ms.openlocfilehash: 86402abca5386f34256f1f44f674f1e1898ad5fd
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500352"
---
# <a name="icorprofilercallbackclassunloadstarted-method"></a><span data-ttu-id="0e463-102">ICorProfilerCallback::ClassUnloadStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="0e463-102">ICorProfilerCallback::ClassUnloadStarted Method</span></span>
<span data-ttu-id="0e463-103">クラスがアンロードされていることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="0e463-103">Notifies the profiler that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e463-104">構文</span><span class="sxs-lookup"><span data-stu-id="0e463-104">Syntax</span></span>  
  
```cpp  
HRESULT ClassUnloadStarted(  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e463-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0e463-105">Parameters</span></span>

- `classId`

  <span data-ttu-id="0e463-106">\[in] は、アンロードするクラスを識別します。</span><span class="sxs-lookup"><span data-stu-id="0e463-106">\[in] Identifies the class that is being unloaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="0e463-107">解説</span><span class="sxs-lookup"><span data-stu-id="0e463-107">Remarks</span></span>  
 <span data-ttu-id="0e463-108">`classId`メソッドから制御が戻った後、の値は情報要求に対して無効です `ClassUnloadStarted` 。このクラスに関する情報を取得するのは、プロファイラーの最後の機会です。</span><span class="sxs-lookup"><span data-stu-id="0e463-108">The value of `classId` is not valid for an information request after the `ClassUnloadStarted` method returns — this is the profiler's last chance to obtain information about this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e463-109">要件</span><span class="sxs-lookup"><span data-stu-id="0e463-109">Requirements</span></span>  
 <span data-ttu-id="0e463-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e463-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e463-111">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0e463-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0e463-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0e463-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0e463-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e463-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e463-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="0e463-114">See also</span></span>

- [<span data-ttu-id="0e463-115">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0e463-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="0e463-116">ClassUnloadFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="0e463-116">ClassUnloadFinished Method</span></span>](icorprofilercallback-classunloadfinished-method.md)
