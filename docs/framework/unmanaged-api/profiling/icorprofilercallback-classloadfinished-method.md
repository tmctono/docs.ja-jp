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
ms.openlocfilehash: ef2c518f8f3f3069e93f06de89add1385cb4e45e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445124"
---
# <a name="icorprofilercallbackclassloadfinished-method"></a><span data-ttu-id="61bbe-102">ICorProfilerCallback::ClassLoadFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="61bbe-102">ICorProfilerCallback::ClassLoadFinished Method</span></span>
<span data-ttu-id="61bbe-103">クラスが読み込みを完了したことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="61bbe-103">Notifies the profiler that a class has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61bbe-104">構文</span><span class="sxs-lookup"><span data-stu-id="61bbe-104">Syntax</span></span>  
  
```cpp  
HRESULT ClassLoadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="61bbe-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="61bbe-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="61bbe-106">から読み込まれたクラスを識別します。</span><span class="sxs-lookup"><span data-stu-id="61bbe-106">[in] Identifies the class that was loaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="61bbe-107">からクラスが正常に読み込まれたかどうかを示す HRESULT。</span><span class="sxs-lookup"><span data-stu-id="61bbe-107">[in] An HRESULT that indicates whether the class loaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="61bbe-108">コメント</span><span class="sxs-lookup"><span data-stu-id="61bbe-108">Remarks</span></span>  
 <span data-ttu-id="61bbe-109">`classId` の値は、`ClassLoadFinished` メソッドが呼び出されるまで、情報要求に対して有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="61bbe-109">The value of `classId` is not valid for an information request until the `ClassLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="61bbe-110">`ClassLoadFinished` コールバックの後も、クラスの読み込みの一部が続行される場合があります。</span><span class="sxs-lookup"><span data-stu-id="61bbe-110">Some parts of loading the class might continue after the `ClassLoadFinished` callback.</span></span> <span data-ttu-id="61bbe-111">`hrStatus` のエラー HRESULT はエラーを示します。</span><span class="sxs-lookup"><span data-stu-id="61bbe-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="61bbe-112">ただし、`hrStatus` の成功 HRESULT は、クラスの読み込みの最初の部分が成功したことのみを示します。</span><span class="sxs-lookup"><span data-stu-id="61bbe-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the class has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61bbe-113">要件</span><span class="sxs-lookup"><span data-stu-id="61bbe-113">Requirements</span></span>  
 <span data-ttu-id="61bbe-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61bbe-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61bbe-115">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="61bbe-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="61bbe-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="61bbe-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="61bbe-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61bbe-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61bbe-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="61bbe-118">See also</span></span>

- [<span data-ttu-id="61bbe-119">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="61bbe-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="61bbe-120">ClassLoadStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="61bbe-120">ClassLoadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)
