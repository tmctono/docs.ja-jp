---
title: ICorProfilerCallback2::ThreadNameChanged メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.ThreadNameChanged
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::ThreadNameChanged
helpviewer_keywords:
- ThreadNameChanged method [.NET Framework profiling]
- ICorProfilerCallback2::ThreadNameChanged method [.NET Framework profiling]
ms.assetid: c8bbd76d-a9ff-44f2-87a6-be052819da36
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dbd9374decdce171d45e57512470c652abc24882
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782630"
---
# <a name="icorprofilercallback2threadnamechanged-method"></a><span data-ttu-id="7d43a-102">ICorProfilerCallback2::ThreadNameChanged メソッド</span><span class="sxs-lookup"><span data-stu-id="7d43a-102">ICorProfilerCallback2::ThreadNameChanged Method</span></span>
<span data-ttu-id="7d43a-103">スレッドの名前が変更されたことをコード プロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="7d43a-103">Notifies the code profiler that the name of a thread has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d43a-104">構文</span><span class="sxs-lookup"><span data-stu-id="7d43a-104">Syntax</span></span>  
  
```  
HRESULT ThreadNameChanged(  
    [in] ThreadID threadId,  
    [in] ULONG cchName,  
    [in] WCHAR name[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d43a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7d43a-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="7d43a-106">[in]スレッドの ID。</span><span class="sxs-lookup"><span data-stu-id="7d43a-106">[in] The ID of the thread.</span></span>  
  
 `cchName`  
 <span data-ttu-id="7d43a-107">[in]スレッドの新しい名前の長さ。</span><span class="sxs-lookup"><span data-stu-id="7d43a-107">[in] The length of the new name of the thread.</span></span>  
  
 `name`  
 <span data-ttu-id="7d43a-108">[in]スレッドの新しい名前。</span><span class="sxs-lookup"><span data-stu-id="7d43a-108">[in] The new name of the thread.</span></span> <span data-ttu-id="7d43a-109">名前が null で終了していません。</span><span class="sxs-lookup"><span data-stu-id="7d43a-109">The name is not null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d43a-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="7d43a-110">Requirements</span></span>  
 <span data-ttu-id="7d43a-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d43a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d43a-112">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7d43a-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7d43a-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7d43a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7d43a-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d43a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d43a-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="7d43a-115">See also</span></span>

- [<span data-ttu-id="7d43a-116">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7d43a-116">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="7d43a-117">ICorProfilerCallback2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7d43a-117">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
