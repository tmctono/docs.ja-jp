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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f86c680a10a3dcb1009b4f0cedd777ab9da5ac1f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57501748"
---
# <a name="icorprofilerinfoendinprocdebugging-method"></a><span data-ttu-id="0884c-102">ICorProfilerInfo::EndInprocDebugging メソッド</span><span class="sxs-lookup"><span data-stu-id="0884c-102">ICorProfilerInfo::EndInprocDebugging Method</span></span>
<span data-ttu-id="0884c-103">プロセスでのデバッグ セッションを停止します。</span><span class="sxs-lookup"><span data-stu-id="0884c-103">Shuts down an in-process debugging session.</span></span> <span data-ttu-id="0884c-104">このメソッドは、.NET Framework version 2.0 で廃止されています。</span><span class="sxs-lookup"><span data-stu-id="0884c-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0884c-105">構文</span><span class="sxs-lookup"><span data-stu-id="0884c-105">Syntax</span></span>  
  
```  
HRESULT EndInprocDebugging(  
    [in]  DWORD dwProfilerContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0884c-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0884c-106">Parameters</span></span>  
 `dwProfilerContext`  
 <span data-ttu-id="0884c-107">[in]デバッグ セッションを識別する値。</span><span class="sxs-lookup"><span data-stu-id="0884c-107">[in] A value that identifies the debugging session.</span></span> <span data-ttu-id="0884c-108">この値はで受信したのと同じである必要があります、 [icorprofilerinfo::begininprocdebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="0884c-108">This value must be the same as that received in the [ICorProfilerInfo::BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0884c-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="0884c-109">Remarks</span></span>  
 <span data-ttu-id="0884c-110">呼び出す必要があります[icorprofilerinfo::begininprocdebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md)と`EndInprocDebugging`内、同じコールバック メソッド。</span><span class="sxs-lookup"><span data-stu-id="0884c-110">You must call [ICorProfilerInfo::BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) and `EndInprocDebugging` within the same callback method.</span></span>  
  
 <span data-ttu-id="0884c-111">CLR デバッグ サービスでは、.NET Framework version 1.0 および 1.1 での制限、インプロセス デバッグがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="0884c-111">The CLR debugging services supported limited in-process debugging in the .NET Framework versions 1.0 and 1.1.</span></span> <span data-ttu-id="0884c-112">インプロセス デバッグするには、デバッグ API の検査の部分を使用するプロファイラーを有効になっています。</span><span class="sxs-lookup"><span data-stu-id="0884c-112">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="0884c-113">ただし、お客様のフィードバックによりインプロセス デバッグが version 2.0、.NET Framework から削除され、プロファイル API に合わせてさらには、機能のセットに置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="0884c-113">However, due to customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0884c-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="0884c-114">Requirements</span></span>  
 <span data-ttu-id="0884c-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0884c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0884c-116">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0884c-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0884c-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0884c-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0884c-118">**.NET framework のバージョン:** 1</span><span class="sxs-lookup"><span data-stu-id="0884c-118">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0884c-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="0884c-119">See also</span></span>
- [<span data-ttu-id="0884c-120">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0884c-120">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
