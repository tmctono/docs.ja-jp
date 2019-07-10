---
title: ICorProfilerInfo::BeginInprocDebugging メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.BeginInprocDebugging
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::BeginInprocDebugging
helpviewer_keywords:
- BeginInprocDebugging method [.NET Framework profiling]
- ICorProfilerInfo::BeginInprocDebugging method [.NET Framework profiling]
ms.assetid: c5c82c69-99f8-4447-aee0-42cca0a5eb5c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 618be7482616ea155798973d02a90f32d46164db
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780263"
---
# <a name="icorprofilerinfobegininprocdebugging-method"></a><span data-ttu-id="903f9-102">ICorProfilerInfo::BeginInprocDebugging メソッド</span><span class="sxs-lookup"><span data-stu-id="903f9-102">ICorProfilerInfo::BeginInprocDebugging Method</span></span>
<span data-ttu-id="903f9-103">初期化します、インプロセス デバッグのサポート。</span><span class="sxs-lookup"><span data-stu-id="903f9-103">Initializes in-process debugging support.</span></span> <span data-ttu-id="903f9-104">このメソッドは、.NET Framework version 2.0 で廃止されています。</span><span class="sxs-lookup"><span data-stu-id="903f9-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="903f9-105">構文</span><span class="sxs-lookup"><span data-stu-id="903f9-105">Syntax</span></span>  
  
```cpp  
HRESULT BeginInprocDebugging(  
    [in]  BOOL   fThisThreadOnly,  
    [out] DWORD *pdwProfilerContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="903f9-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="903f9-106">Parameters</span></span>  
 `fThisThreadOnly`  
 <span data-ttu-id="903f9-107">[in]この値に設定`true`現在スレッドのみのデバッグのサポートを初期化するために設定`false`のすべてのスレッドのデバッグのサポートを初期化します。</span><span class="sxs-lookup"><span data-stu-id="903f9-107">[in] Set this value to `true` to initialize debugging support for only the current thread; set it to `false` to initialize debugging support for all threads.</span></span>  
  
 `pdwProfilerContext`  
 <span data-ttu-id="903f9-108">[out]デバッグ セッションを識別する戻り値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="903f9-108">[out] The pointer to a returned value that identifies the debugging session.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="903f9-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="903f9-109">Remarks</span></span>  
 <span data-ttu-id="903f9-110">CLR デバッグ サービスでは、.NET Framework version 1.0 および 1.1 での制限、インプロセス デバッグがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="903f9-110">The CLR debugging services supported limited in-process debugging in the .NET Framework versions 1.0 and 1.1.</span></span> <span data-ttu-id="903f9-111">インプロセス デバッグするには、デバッグ API の検査の部分を使用するプロファイラーを有効になっています。</span><span class="sxs-lookup"><span data-stu-id="903f9-111">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="903f9-112">ただし、お客様のフィードバックによりインプロセス デバッグが version 2.0、.NET Framework から削除され、プロファイル API に合わせてさらには、機能のセットに置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="903f9-112">However, due to customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="903f9-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="903f9-113">Requirements</span></span>  
 <span data-ttu-id="903f9-114">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="903f9-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="903f9-115">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="903f9-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="903f9-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="903f9-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="903f9-117">**.NET framework のバージョン:** 1</span><span class="sxs-lookup"><span data-stu-id="903f9-117">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="903f9-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="903f9-118">See also</span></span>

- [<span data-ttu-id="903f9-119">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="903f9-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
