---
title: ICorProfilerCallback::ClassLoadFinished メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassLoadFinished
helpviewer_keywords:
- ClassLoadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ClassLoadFinished method [.NET Framework profiling]
ms.assetid: 3dd80fbe-d62d-4d4d-acf8-5b7d0efe607e
topic_type:
- apiref
ms.openlocfilehash: e0ff90f99c1127b5a4626f47514ba7099b5d48af
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866599"
---
# <a name="icorprofilercallbackclassloadfinished-method"></a><span data-ttu-id="b6d13-102">ICorProfilerCallback::ClassLoadFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="b6d13-102">ICorProfilerCallback::ClassLoadFinished Method</span></span>
<span data-ttu-id="b6d13-103">クラスが読み込みを完了したことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="b6d13-103">Notifies the profiler that a class has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6d13-104">構文</span><span class="sxs-lookup"><span data-stu-id="b6d13-104">Syntax</span></span>  
  
```cpp  
HRESULT ClassLoadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6d13-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b6d13-105">Parameters</span></span>

- `classId`

  <span data-ttu-id="b6d13-106">の \[] は、読み込まれたクラスを識別します。</span><span class="sxs-lookup"><span data-stu-id="b6d13-106">\[in] Identifies the class that was loaded.</span></span>

- `hrStatus`

  <span data-ttu-id="b6d13-107">\[]) クラスが正常に読み込まれたかどうかを示す HRESULT。</span><span class="sxs-lookup"><span data-stu-id="b6d13-107">\[in] An HRESULT that indicates whether the class loaded successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="b6d13-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="b6d13-108">Remarks</span></span>  
 <span data-ttu-id="b6d13-109">`classId` の値は、`ClassLoadFinished` メソッドが呼び出されるまで、情報要求に対して有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="b6d13-109">The value of `classId` is not valid for an information request until the `ClassLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="b6d13-110">`ClassLoadFinished` コールバックの後も、クラスの読み込みの一部が続行される場合があります。</span><span class="sxs-lookup"><span data-stu-id="b6d13-110">Some parts of loading the class might continue after the `ClassLoadFinished` callback.</span></span> <span data-ttu-id="b6d13-111">`hrStatus` のエラー HRESULT はエラーを示します。</span><span class="sxs-lookup"><span data-stu-id="b6d13-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="b6d13-112">ただし、`hrStatus` の成功 HRESULT は、クラスの読み込みの最初の部分が成功したことのみを示します。</span><span class="sxs-lookup"><span data-stu-id="b6d13-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the class has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6d13-113">要件</span><span class="sxs-lookup"><span data-stu-id="b6d13-113">Requirements</span></span>  
 <span data-ttu-id="b6d13-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6d13-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6d13-115">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b6d13-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b6d13-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b6d13-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b6d13-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6d13-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6d13-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="b6d13-118">See also</span></span>

- [<span data-ttu-id="b6d13-119">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b6d13-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="b6d13-120">ClassLoadStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="b6d13-120">ClassLoadStarted Method</span></span>](icorprofilercallback-classloadstarted-method.md)
