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
ms.openlocfilehash: 70535f8bcee95c2596c43617eb5893e2d92a355b
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84496782"
---
# <a name="icorprofilerinfo2getthreadappdomain-method"></a><span data-ttu-id="ba723-102">ICorProfilerInfo2::GetThreadAppDomain メソッド</span><span class="sxs-lookup"><span data-stu-id="ba723-102">ICorProfilerInfo2::GetThreadAppDomain Method</span></span>
<span data-ttu-id="ba723-103">指定したスレッドが現在コードを実行しているアプリケーションドメインの ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="ba723-103">Gets the ID of the application domain in which the specified thread is currently executing code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba723-104">構文</span><span class="sxs-lookup"><span data-stu-id="ba723-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadAppDomain(  
    [in]  ThreadID threadId,  
    [out] AppDomainID *pAppDomainId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba723-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ba723-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="ba723-106">からスレッドを指定する ID。</span><span class="sxs-lookup"><span data-stu-id="ba723-106">[in] The ID specifying the thread.</span></span>  
  
 `pAppDomainId`  
 <span data-ttu-id="ba723-107">入出力アプリケーションドメインの ID へのポインター。</span><span class="sxs-lookup"><span data-stu-id="ba723-107">[out] A pointer to the ID of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba723-108">要件</span><span class="sxs-lookup"><span data-stu-id="ba723-108">Requirements</span></span>  
 <span data-ttu-id="ba723-109">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba723-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba723-110">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ba723-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ba723-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ba723-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ba723-112">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba723-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba723-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="ba723-113">See also</span></span>

- [<span data-ttu-id="ba723-114">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ba723-114">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="ba723-115">ICorProfilerInfo2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ba723-115">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
