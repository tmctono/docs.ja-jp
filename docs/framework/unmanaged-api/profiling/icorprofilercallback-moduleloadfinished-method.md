---
title: ICorProfilerCallback::ModuleLoadFinished メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleLoadFinished
helpviewer_keywords:
- ModuleLoadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ModuleLoadFinished method [.NET Framework profiling]
ms.assetid: 050649e5-ffc0-4458-a0a4-d9ee128a219e
topic_type:
- apiref
ms.openlocfilehash: 481fc2c40331e31f6a018d012fb2b2543d4fd9b5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503368"
---
# <a name="icorprofilercallbackmoduleloadfinished-method"></a><span data-ttu-id="d1e4f-102">ICorProfilerCallback::ModuleLoadFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="d1e4f-102">ICorProfilerCallback::ModuleLoadFinished Method</span></span>
<span data-ttu-id="d1e4f-103">モジュールが読み込みを終了したことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="d1e4f-103">Notifies the profiler that a module has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1e4f-104">構文</span><span class="sxs-lookup"><span data-stu-id="d1e4f-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleLoadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d1e4f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d1e4f-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="d1e4f-106">から読み込みを終了したモジュールの ID。</span><span class="sxs-lookup"><span data-stu-id="d1e4f-106">[in] The ID of the module that has finished loading.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="d1e4f-107">からモジュールが正常に読み込まれたかどうかを示す HRESULT。</span><span class="sxs-lookup"><span data-stu-id="d1e4f-107">[in] An HRESULT that indicates whether the module was loaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d1e4f-108">解説</span><span class="sxs-lookup"><span data-stu-id="d1e4f-108">Remarks</span></span>  
 <span data-ttu-id="d1e4f-109">の値 `moduleId` は、 `ModuleLoadFinished` メソッドが呼び出されるまで、情報要求に対して有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="d1e4f-109">The value of `moduleId` is not valid for an information request until the `ModuleLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="d1e4f-110">モジュールの読み込みの一部は、コールバック後に続行される場合があり `ModuleLoadFinished` ます。</span><span class="sxs-lookup"><span data-stu-id="d1e4f-110">Some parts of loading the module might continue after the `ModuleLoadFinished` callback.</span></span> <span data-ttu-id="d1e4f-111">のエラー HRESULT は `hrStatus` エラーを示します。</span><span class="sxs-lookup"><span data-stu-id="d1e4f-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="d1e4f-112">ただし、の成功 HRESULT は、 `hrStatus` モジュールの読み込みの最初の部分が成功したことを示します。</span><span class="sxs-lookup"><span data-stu-id="d1e4f-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the module has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1e4f-113">要件</span><span class="sxs-lookup"><span data-stu-id="d1e4f-113">Requirements</span></span>  
 <span data-ttu-id="d1e4f-114">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1e4f-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1e4f-115">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d1e4f-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d1e4f-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d1e4f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d1e4f-117">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1e4f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1e4f-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="d1e4f-118">See also</span></span>

- [<span data-ttu-id="d1e4f-119">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d1e4f-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="d1e4f-120">ModuleLoadStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="d1e4f-120">ModuleLoadStarted Method</span></span>](icorprofilercallback-moduleloadstarted-method.md)
