---
title: ICorProfilerInfo2::GetThreadAppDomain メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetThreadAppDomain
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetThreadAppDomain
helpviewer_keywords:
- ICorProfilerInfo2::GetThreadAppDomain method [.NET Framework profiling]
- GetThreadAppDomain method [.NET Framework profiling]
ms.assetid: 4a11b264-8540-4732-aa35-bc2d95b95b8e
topic_type:
- apiref
ms.openlocfilehash: 7c1ee1c39fbf2dcc1f16df3bc94a235676a216dd
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862569"
---
# <a name="icorprofilerinfo2getthreadappdomain-method"></a><span data-ttu-id="7c30c-102">ICorProfilerInfo2::GetThreadAppDomain メソッド</span><span class="sxs-lookup"><span data-stu-id="7c30c-102">ICorProfilerInfo2::GetThreadAppDomain Method</span></span>
<span data-ttu-id="7c30c-103">指定したスレッドが現在コードを実行しているアプリケーションドメインの ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="7c30c-103">Gets the ID of the application domain in which the specified thread is currently executing code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c30c-104">構文</span><span class="sxs-lookup"><span data-stu-id="7c30c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadAppDomain(  
    [in]  ThreadID threadId,  
    [out] AppDomainID *pAppDomainId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c30c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7c30c-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="7c30c-106">からスレッドを指定する ID。</span><span class="sxs-lookup"><span data-stu-id="7c30c-106">[in] The ID specifying the thread.</span></span>  
  
 `pAppDomainId`  
 <span data-ttu-id="7c30c-107">入出力アプリケーションドメインの ID へのポインター。</span><span class="sxs-lookup"><span data-stu-id="7c30c-107">[out] A pointer to the ID of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c30c-108">要件</span><span class="sxs-lookup"><span data-stu-id="7c30c-108">Requirements</span></span>  
 <span data-ttu-id="7c30c-109">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c30c-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c30c-110">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7c30c-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7c30c-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c30c-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7c30c-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c30c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c30c-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="7c30c-113">See also</span></span>

- [<span data-ttu-id="7c30c-114">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7c30c-114">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="7c30c-115">ICorProfilerInfo2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7c30c-115">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
