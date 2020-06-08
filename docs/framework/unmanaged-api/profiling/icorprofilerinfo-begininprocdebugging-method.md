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
ms.openlocfilehash: f0b118ef109d0adb17a28b60c091390b8e4280c9
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84498662"
---
# <a name="icorprofilerinfobegininprocdebugging-method"></a><span data-ttu-id="f595b-102">ICorProfilerInfo::BeginInprocDebugging メソッド</span><span class="sxs-lookup"><span data-stu-id="f595b-102">ICorProfilerInfo::BeginInprocDebugging Method</span></span>
<span data-ttu-id="f595b-103">インプロセスデバッグサポートを初期化します。</span><span class="sxs-lookup"><span data-stu-id="f595b-103">Initializes in-process debugging support.</span></span> <span data-ttu-id="f595b-104">このメソッドは .NET Framework バージョン2.0 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="f595b-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f595b-105">構文</span><span class="sxs-lookup"><span data-stu-id="f595b-105">Syntax</span></span>  
  
```cpp  
HRESULT BeginInprocDebugging(  
    [in]  BOOL   fThisThreadOnly,  
    [out] DWORD *pdwProfilerContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f595b-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f595b-106">Parameters</span></span>  
 `fThisThreadOnly`  
 <span data-ttu-id="f595b-107">から現在のスレッドのみのデバッグサポートを初期化するには、この値をに設定し `true` ます。 `false` すべてのスレッドのデバッグサポートを初期化するには、をに設定します。</span><span class="sxs-lookup"><span data-stu-id="f595b-107">[in] Set this value to `true` to initialize debugging support for only the current thread; set it to `false` to initialize debugging support for all threads.</span></span>  
  
 `pdwProfilerContext`  
 <span data-ttu-id="f595b-108">入出力デバッグセッションを識別する戻り値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="f595b-108">[out] The pointer to a returned value that identifies the debugging session.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f595b-109">解説</span><span class="sxs-lookup"><span data-stu-id="f595b-109">Remarks</span></span>  
 <span data-ttu-id="f595b-110">CLR デバッグサービスでは、.NET Framework バージョン1.0 および1.1 でサポートされているプロセス内デバッグが制限されています。</span><span class="sxs-lookup"><span data-stu-id="f595b-110">The CLR debugging services supported limited in-process debugging in the .NET Framework versions 1.0 and 1.1.</span></span> <span data-ttu-id="f595b-111">インプロセスデバッグでは、デバッグ API の検査部分を使用するプロファイラーが有効になりました。</span><span class="sxs-lookup"><span data-stu-id="f595b-111">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="f595b-112">ただし、お客様からのフィードバックにより、プロセス内デバッグはバージョン2.0 の .NET Framework から削除され、プロファイル API により多くの機能を備えた一連の機能に置き換えられました。</span><span class="sxs-lookup"><span data-stu-id="f595b-112">However, due to customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f595b-113">要件</span><span class="sxs-lookup"><span data-stu-id="f595b-113">Requirements</span></span>  
 <span data-ttu-id="f595b-114">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f595b-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f595b-115">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f595b-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f595b-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f595b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f595b-117">**.NET Framework のバージョン:** 1.0</span><span class="sxs-lookup"><span data-stu-id="f595b-117">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f595b-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="f595b-118">See also</span></span>

- [<span data-ttu-id="f595b-119">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f595b-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
