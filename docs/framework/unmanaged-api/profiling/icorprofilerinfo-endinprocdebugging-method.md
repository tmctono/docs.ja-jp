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
ms.openlocfilehash: afbb007b6293e6e9cff92281a6f5e93b1e7924ec
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502978"
---
# <a name="icorprofilerinfoendinprocdebugging-method"></a><span data-ttu-id="dec05-102">ICorProfilerInfo::EndInprocDebugging メソッド</span><span class="sxs-lookup"><span data-stu-id="dec05-102">ICorProfilerInfo::EndInprocDebugging Method</span></span>
<span data-ttu-id="dec05-103">インプロセスデバッグセッションをシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="dec05-103">Shuts down an in-process debugging session.</span></span> <span data-ttu-id="dec05-104">このメソッドは .NET Framework バージョン2.0 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="dec05-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dec05-105">構文</span><span class="sxs-lookup"><span data-stu-id="dec05-105">Syntax</span></span>  
  
```cpp  
HRESULT EndInprocDebugging(  
    [in]  DWORD dwProfilerContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dec05-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dec05-106">Parameters</span></span>  
 `dwProfilerContext`  
 <span data-ttu-id="dec05-107">からデバッグセッションを識別する値。</span><span class="sxs-lookup"><span data-stu-id="dec05-107">[in] A value that identifies the debugging session.</span></span> <span data-ttu-id="dec05-108">この値は、 [ICorProfilerInfo:: BeginInprocDebugging](icorprofilerinfo-begininprocdebugging-method.md)メソッドで受け取った値と同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="dec05-108">This value must be the same as that received in the [ICorProfilerInfo::BeginInprocDebugging](icorprofilerinfo-begininprocdebugging-method.md) method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dec05-109">解説</span><span class="sxs-lookup"><span data-stu-id="dec05-109">Remarks</span></span>  
 <span data-ttu-id="dec05-110">同じコールバックメソッド内で[ICorProfilerInfo:: BeginInprocDebugging](icorprofilerinfo-begininprocdebugging-method.md)およびを呼び出す必要があり `EndInprocDebugging` ます。</span><span class="sxs-lookup"><span data-stu-id="dec05-110">You must call [ICorProfilerInfo::BeginInprocDebugging](icorprofilerinfo-begininprocdebugging-method.md) and `EndInprocDebugging` within the same callback method.</span></span>  
  
 <span data-ttu-id="dec05-111">CLR デバッグサービスでは、.NET Framework バージョン1.0 および1.1 でサポートされているプロセス内デバッグが制限されています。</span><span class="sxs-lookup"><span data-stu-id="dec05-111">The CLR debugging services supported limited in-process debugging in the .NET Framework versions 1.0 and 1.1.</span></span> <span data-ttu-id="dec05-112">インプロセスデバッグでは、デバッグ API の検査部分を使用するプロファイラーが有効になりました。</span><span class="sxs-lookup"><span data-stu-id="dec05-112">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="dec05-113">ただし、お客様からのフィードバックにより、プロセス内デバッグはバージョン2.0 の .NET Framework から削除され、プロファイル API により多くの機能を備えた一連の機能に置き換えられました。</span><span class="sxs-lookup"><span data-stu-id="dec05-113">However, due to customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dec05-114">要件</span><span class="sxs-lookup"><span data-stu-id="dec05-114">Requirements</span></span>  
 <span data-ttu-id="dec05-115">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dec05-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dec05-116">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="dec05-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="dec05-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dec05-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dec05-118">**.NET Framework のバージョン:** 1.0</span><span class="sxs-lookup"><span data-stu-id="dec05-118">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dec05-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="dec05-119">See also</span></span>

- [<span data-ttu-id="dec05-120">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dec05-120">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
