---
title: ICorProfilerInfo::GetHandleFromThread メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetHandleFromThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetHandleFromThread
helpviewer_keywords:
- GetHandleFromThread method [.NET Framework profiling]
- ICorProfilerInfo::GetHandleFromThread method [.NET Framework profiling]
ms.assetid: 36cdc9f5-7579-4cd2-aa36-fc05c741584c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: be8f4e396171f3e56b5b93969d3960b7aaea142e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780649"
---
# <a name="icorprofilerinfogethandlefromthread-method"></a><span data-ttu-id="f2cb1-102">ICorProfilerInfo::GetHandleFromThread メソッド</span><span class="sxs-lookup"><span data-stu-id="f2cb1-102">ICorProfilerInfo::GetHandleFromThread Method</span></span>
<span data-ttu-id="f2cb1-103">Win32 スレッドのハンドル、スレッドの ID にマップします。</span><span class="sxs-lookup"><span data-stu-id="f2cb1-103">Maps the ID of a thread to a Win32 thread handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2cb1-104">構文</span><span class="sxs-lookup"><span data-stu-id="f2cb1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHandleFromThread(  
    [in]  ThreadID threadId,  
    [out] HANDLE  *phThread);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2cb1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f2cb1-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="f2cb1-106">[in]マップされることをスレッド ID です。</span><span class="sxs-lookup"><span data-stu-id="f2cb1-106">[in] The thread ID to be mapped.</span></span>  
  
 `phThread`  
 <span data-ttu-id="f2cb1-107">[out]Win32 スレッドのハンドルへのポインター。</span><span class="sxs-lookup"><span data-stu-id="f2cb1-107">[out] A pointer to a Win32 thread handle.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f2cb1-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="f2cb1-108">Remarks</span></span>  
 <span data-ttu-id="f2cb1-109">プロファイラーは、Win32 を呼び出す必要があります`DuplicateHandle`関数を使用する前に、ハンドル。</span><span class="sxs-lookup"><span data-stu-id="f2cb1-109">The profiler must call the Win32 `DuplicateHandle` function on the handle before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2cb1-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="f2cb1-110">Requirements</span></span>  
 <span data-ttu-id="f2cb1-111">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2cb1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2cb1-112">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f2cb1-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f2cb1-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f2cb1-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f2cb1-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2cb1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2cb1-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="f2cb1-115">See also</span></span>

- [<span data-ttu-id="f2cb1-116">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f2cb1-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
