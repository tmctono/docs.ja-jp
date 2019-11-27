---
title: ICorProfilerInfo::EndInprocDebugging メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.EndInprocDebugging
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::EndInprocDebugging
helpviewer_keywords:
- ICorProfilerInfo::EndInprocDebugging method [.NET Framework profiling]
- EndInprocDebugging method [.NET Framework profiling]
ms.assetid: 35bc1188-9767-4141-8038-60ea015b99ac
topic_type:
- apiref
ms.openlocfilehash: 09b1b81bde486db67acede99e0d67ff85cb01bae
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447757"
---
# <a name="icorprofilerinfoendinprocdebugging-method"></a><span data-ttu-id="58ebb-102">ICorProfilerInfo::EndInprocDebugging メソッド</span><span class="sxs-lookup"><span data-stu-id="58ebb-102">ICorProfilerInfo::EndInprocDebugging Method</span></span>
<span data-ttu-id="58ebb-103">インプロセスデバッグセッションをシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="58ebb-103">Shuts down an in-process debugging session.</span></span> <span data-ttu-id="58ebb-104">このメソッドは .NET Framework バージョン2.0 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="58ebb-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58ebb-105">構文</span><span class="sxs-lookup"><span data-stu-id="58ebb-105">Syntax</span></span>  
  
```cpp  
HRESULT EndInprocDebugging(  
    [in]  DWORD dwProfilerContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58ebb-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="58ebb-106">Parameters</span></span>  
 `dwProfilerContext`  
 <span data-ttu-id="58ebb-107">からデバッグセッションを識別する値。</span><span class="sxs-lookup"><span data-stu-id="58ebb-107">[in] A value that identifies the debugging session.</span></span> <span data-ttu-id="58ebb-108">この値は、 [ICorProfilerInfo:: BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md)メソッドで受け取った値と同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="58ebb-108">This value must be the same as that received in the [ICorProfilerInfo::BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="58ebb-109">コメント</span><span class="sxs-lookup"><span data-stu-id="58ebb-109">Remarks</span></span>  
 <span data-ttu-id="58ebb-110">同じコールバックメソッド内で[ICorProfilerInfo:: BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md)と `EndInprocDebugging` を呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="58ebb-110">You must call [ICorProfilerInfo::BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) and `EndInprocDebugging` within the same callback method.</span></span>  
  
 <span data-ttu-id="58ebb-111">CLR デバッグサービスでは、.NET Framework バージョン1.0 および1.1 でサポートされているプロセス内デバッグが制限されています。</span><span class="sxs-lookup"><span data-stu-id="58ebb-111">The CLR debugging services supported limited in-process debugging in the .NET Framework versions 1.0 and 1.1.</span></span> <span data-ttu-id="58ebb-112">インプロセスデバッグでは、デバッグ API の検査部分を使用するプロファイラーが有効になりました。</span><span class="sxs-lookup"><span data-stu-id="58ebb-112">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="58ebb-113">ただし、お客様からのフィードバックにより、プロセス内デバッグはバージョン2.0 の .NET Framework から削除され、プロファイル API により多くの機能を備えた一連の機能に置き換えられました。</span><span class="sxs-lookup"><span data-stu-id="58ebb-113">However, due to customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58ebb-114">要件</span><span class="sxs-lookup"><span data-stu-id="58ebb-114">Requirements</span></span>  
 <span data-ttu-id="58ebb-115">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58ebb-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58ebb-116">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="58ebb-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="58ebb-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="58ebb-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="58ebb-118">**.NET Framework のバージョン:** 1.0</span><span class="sxs-lookup"><span data-stu-id="58ebb-118">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58ebb-119">参照</span><span class="sxs-lookup"><span data-stu-id="58ebb-119">See also</span></span>

- [<span data-ttu-id="58ebb-120">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="58ebb-120">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
