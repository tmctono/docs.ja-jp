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
ms.openlocfilehash: 15ce195af0c0e8f8777f6e5d02043e17e32308da
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866651"
---
# <a name="icorprofilercallbackassemblyloadfinished-method"></a><span data-ttu-id="09a88-102">ICorProfilerCallback::AssemblyLoadFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="09a88-102">ICorProfilerCallback::AssemblyLoadFinished Method</span></span>
<span data-ttu-id="09a88-103">アセンブリの読み込みが完了したことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="09a88-103">Notifies the profiler that an assembly has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09a88-104">構文</span><span class="sxs-lookup"><span data-stu-id="09a88-104">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyLoadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09a88-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="09a88-105">Parameters</span></span>

- `assemblyId`

  <span data-ttu-id="09a88-106">の \[] は、読み込まれたアセンブリを識別します。</span><span class="sxs-lookup"><span data-stu-id="09a88-106">\[in] Identifies the assembly that was loaded.</span></span>

- `hrStatus`

  <span data-ttu-id="09a88-107">\[] アセンブリの読み込みが正常に終了したかどうかを示す HRESULT。</span><span class="sxs-lookup"><span data-stu-id="09a88-107">\[in] An HRESULT that indicates whether the assembly finished loading successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="09a88-108">コメント</span><span class="sxs-lookup"><span data-stu-id="09a88-108">Remarks</span></span>  
 <span data-ttu-id="09a88-109">`assemblyId` の値は、`AssemblyLoadFinished` メソッドが呼び出されるまで、情報要求に対して有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="09a88-109">The value of `assemblyId` is not valid for an information request until the `AssemblyLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="09a88-110">`AssemblyLoadFinished` コールバックの後も、アセンブリの読み込みの一部が続行される場合があります。</span><span class="sxs-lookup"><span data-stu-id="09a88-110">Some parts of loading the assembly might continue after the `AssemblyLoadFinished` callback.</span></span> <span data-ttu-id="09a88-111">`hrStatus` のエラー HRESULT はエラーを示します。</span><span class="sxs-lookup"><span data-stu-id="09a88-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="09a88-112">ただし、`hrStatus` の成功 HRESULT は、アセンブリの読み込みの最初の部分が成功したことのみを示します。</span><span class="sxs-lookup"><span data-stu-id="09a88-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09a88-113">要件</span><span class="sxs-lookup"><span data-stu-id="09a88-113">Requirements</span></span>  
 <span data-ttu-id="09a88-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09a88-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09a88-115">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="09a88-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="09a88-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="09a88-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="09a88-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09a88-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09a88-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="09a88-118">See also</span></span>

- [<span data-ttu-id="09a88-119">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="09a88-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
