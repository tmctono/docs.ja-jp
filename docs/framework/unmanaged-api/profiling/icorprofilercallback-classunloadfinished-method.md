---
title: ICorProfilerCallback::ClassUnloadFinished メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassUnloadFinished
helpviewer_keywords:
- ICorProfilerCallback::ClassUnloadFinished method [.NET Framework profiling]
- ClassUnloadFinished method [.NET Framework profiling]
ms.assetid: 55674b68-678a-4747-ae06-4e91519c7305
topic_type:
- apiref
ms.openlocfilehash: 14eb90c707618796d6d62ed2ec5710ceba31ba6c
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500378"
---
# <a name="icorprofilercallbackclassunloadfinished-method"></a><span data-ttu-id="48ec6-102">ICorProfilerCallback::ClassUnloadFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="48ec6-102">ICorProfilerCallback::ClassUnloadFinished Method</span></span>
<span data-ttu-id="48ec6-103">クラスのアンロードが終了したことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="48ec6-103">Notifies the profiler that a class has finished unloading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48ec6-104">構文</span><span class="sxs-lookup"><span data-stu-id="48ec6-104">Syntax</span></span>  
  
```cpp  
HRESULT ClassUnloadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48ec6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="48ec6-105">Parameters</span></span>

- `classId`

  <span data-ttu-id="48ec6-106">\[in] は、アンロードされたクラスを識別します。</span><span class="sxs-lookup"><span data-stu-id="48ec6-106">\[in] Identifies the class that was unloaded.</span></span>

- `hrStatus`

  <span data-ttu-id="48ec6-107">\[in] クラスが正常にアンロードされたかどうかを示す HRESULT。</span><span class="sxs-lookup"><span data-stu-id="48ec6-107">\[in] An HRESULT that indicates whether the class was unloaded successfully.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="48ec6-108">解説</span><span class="sxs-lookup"><span data-stu-id="48ec6-108">Remarks</span></span>  
 <span data-ttu-id="48ec6-109">クラスのアンロードの一部は、コールバック後に続行される場合があり `ClassUnloadFinished` ます。</span><span class="sxs-lookup"><span data-stu-id="48ec6-109">Some parts of unloading the class might continue after the `ClassUnloadFinished` callback.</span></span> <span data-ttu-id="48ec6-110">のエラー HRESULT は `hrStatus` エラーを示します。</span><span class="sxs-lookup"><span data-stu-id="48ec6-110">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="48ec6-111">ただし、の成功 HRESULT は、 `hrStatus` クラスのアンロードの最初の部分が成功したことを示します。</span><span class="sxs-lookup"><span data-stu-id="48ec6-111">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the class has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48ec6-112">要件</span><span class="sxs-lookup"><span data-stu-id="48ec6-112">Requirements</span></span>  
 <span data-ttu-id="48ec6-113">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48ec6-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48ec6-114">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="48ec6-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="48ec6-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="48ec6-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="48ec6-116">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48ec6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48ec6-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="48ec6-117">See also</span></span>

- [<span data-ttu-id="48ec6-118">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="48ec6-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="48ec6-119">ClassUnloadStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="48ec6-119">ClassUnloadStarted Method</span></span>](icorprofilercallback-classunloadstarted-method.md)
