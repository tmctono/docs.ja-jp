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
ms.openlocfilehash: c14979fa711145b9f1a134f90d7450b24e6d8a15
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864298"
---
# <a name="icorprofilerinfobegininprocdebugging-method"></a><span data-ttu-id="a3d79-102">ICorProfilerInfo::BeginInprocDebugging メソッド</span><span class="sxs-lookup"><span data-stu-id="a3d79-102">ICorProfilerInfo::BeginInprocDebugging Method</span></span>
<span data-ttu-id="a3d79-103">インプロセスデバッグサポートを初期化します。</span><span class="sxs-lookup"><span data-stu-id="a3d79-103">Initializes in-process debugging support.</span></span> <span data-ttu-id="a3d79-104">このメソッドは .NET Framework バージョン2.0 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="a3d79-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3d79-105">構文</span><span class="sxs-lookup"><span data-stu-id="a3d79-105">Syntax</span></span>  
  
```cpp  
HRESULT BeginInprocDebugging(  
    [in]  BOOL   fThisThreadOnly,  
    [out] DWORD *pdwProfilerContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3d79-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a3d79-106">Parameters</span></span>  
 `fThisThreadOnly`  
 <span data-ttu-id="a3d79-107">から現在のスレッドのみのデバッグサポートを初期化するには、この値を `true` に設定します。すべてのスレッドのデバッグサポートを初期化するには、`false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="a3d79-107">[in] Set this value to `true` to initialize debugging support for only the current thread; set it to `false` to initialize debugging support for all threads.</span></span>  
  
 `pdwProfilerContext`  
 <span data-ttu-id="a3d79-108">入出力デバッグセッションを識別する戻り値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="a3d79-108">[out] The pointer to a returned value that identifies the debugging session.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a3d79-109">コメント</span><span class="sxs-lookup"><span data-stu-id="a3d79-109">Remarks</span></span>  
 <span data-ttu-id="a3d79-110">CLR デバッグサービスでは、.NET Framework バージョン1.0 および1.1 でサポートされているプロセス内デバッグが制限されています。</span><span class="sxs-lookup"><span data-stu-id="a3d79-110">The CLR debugging services supported limited in-process debugging in the .NET Framework versions 1.0 and 1.1.</span></span> <span data-ttu-id="a3d79-111">インプロセスデバッグでは、デバッグ API の検査部分を使用するプロファイラーが有効になりました。</span><span class="sxs-lookup"><span data-stu-id="a3d79-111">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="a3d79-112">ただし、お客様からのフィードバックにより、プロセス内デバッグはバージョン2.0 の .NET Framework から削除され、プロファイル API により多くの機能を備えた一連の機能に置き換えられました。</span><span class="sxs-lookup"><span data-stu-id="a3d79-112">However, due to customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3d79-113">要件</span><span class="sxs-lookup"><span data-stu-id="a3d79-113">Requirements</span></span>  
 <span data-ttu-id="a3d79-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3d79-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3d79-115">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a3d79-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a3d79-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a3d79-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a3d79-117">**.NET Framework のバージョン:** 1.0</span><span class="sxs-lookup"><span data-stu-id="a3d79-117">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3d79-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="a3d79-118">See also</span></span>

- [<span data-ttu-id="a3d79-119">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a3d79-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
