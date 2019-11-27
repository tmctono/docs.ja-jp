---
title: ICorProfilerCallback::AssemblyLoadFinished メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyLoadFinished
helpviewer_keywords:
- ICorProfilerCallback::AssemblyLoadFinished method [.NET Framework profiling]
- AssemblyLoadFinished method [.NET Framework profiling]
ms.assetid: 86d98f39-52e6-4c61-a625-9760f695ff12
topic_type:
- apiref
ms.openlocfilehash: 33b72c8d089e5b335069fe465987086dfa1243bc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445174"
---
# <a name="icorprofilercallbackassemblyloadfinished-method"></a><span data-ttu-id="0da63-102">ICorProfilerCallback::AssemblyLoadFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="0da63-102">ICorProfilerCallback::AssemblyLoadFinished Method</span></span>
<span data-ttu-id="0da63-103">アセンブリの読み込みが完了したことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="0da63-103">Notifies the profiler that an assembly has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0da63-104">構文</span><span class="sxs-lookup"><span data-stu-id="0da63-104">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyLoadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0da63-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0da63-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="0da63-106">から読み込まれたアセンブリを識別します。</span><span class="sxs-lookup"><span data-stu-id="0da63-106">[in] Identifies the assembly that was loaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="0da63-107">からアセンブリの読み込みが正常に終了したかどうかを示す HRESULT。</span><span class="sxs-lookup"><span data-stu-id="0da63-107">[in] An HRESULT that indicates whether the assembly finished loading successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0da63-108">コメント</span><span class="sxs-lookup"><span data-stu-id="0da63-108">Remarks</span></span>  
 <span data-ttu-id="0da63-109">`assemblyId` の値は、`AssemblyLoadFinished` メソッドが呼び出されるまで、情報要求に対して有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="0da63-109">The value of `assemblyId` is not valid for an information request until the `AssemblyLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="0da63-110">`AssemblyLoadFinished` コールバックの後も、アセンブリの読み込みの一部が続行される場合があります。</span><span class="sxs-lookup"><span data-stu-id="0da63-110">Some parts of loading the assembly might continue after the `AssemblyLoadFinished` callback.</span></span> <span data-ttu-id="0da63-111">`hrStatus` のエラー HRESULT はエラーを示します。</span><span class="sxs-lookup"><span data-stu-id="0da63-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="0da63-112">ただし、`hrStatus` の成功 HRESULT は、アセンブリの読み込みの最初の部分が成功したことのみを示します。</span><span class="sxs-lookup"><span data-stu-id="0da63-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0da63-113">要件</span><span class="sxs-lookup"><span data-stu-id="0da63-113">Requirements</span></span>  
 <span data-ttu-id="0da63-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0da63-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0da63-115">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0da63-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0da63-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0da63-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0da63-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0da63-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0da63-118">参照</span><span class="sxs-lookup"><span data-stu-id="0da63-118">See also</span></span>

- [<span data-ttu-id="0da63-119">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0da63-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
