---
title: ICorProfilerCallback2::HandleDestroyed メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.HandleDestroyed
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::HandleDestroyed
helpviewer_keywords:
- ICorProfilerCallback2::HandleDestroyed method [.NET Framework profiling]
- HandleDestroyed method [.NET Framework profiling]
ms.assetid: ab4f4bbd-40c7-4667-bfde-60cd73803110
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bc6b086b444a769afbf01369b50c69e242a21050
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62041562"
---
# <a name="icorprofilercallback2handledestroyed-method"></a><span data-ttu-id="9e241-102">ICorProfilerCallback2::HandleDestroyed メソッド</span><span class="sxs-lookup"><span data-stu-id="9e241-102">ICorProfilerCallback2::HandleDestroyed Method</span></span>
<span data-ttu-id="9e241-103">ガベージ コレクション ハンドルが破棄されたことをコード プロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="9e241-103">Notifies the code profiler that a garbage collection handle has been destroyed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e241-104">構文</span><span class="sxs-lookup"><span data-stu-id="9e241-104">Syntax</span></span>  
  
```  
HRESULT HandleDestroyed(  
    [in] GCHandleID handleId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e241-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9e241-105">Parameters</span></span>  
 `handleId`  
 <span data-ttu-id="9e241-106">[in]ガベージ コレクション ハンドルの ID。</span><span class="sxs-lookup"><span data-stu-id="9e241-106">[in] The ID of the handle for the garbage collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e241-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="9e241-107">Requirements</span></span>  
 <span data-ttu-id="9e241-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e241-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e241-109">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9e241-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9e241-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9e241-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9e241-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e241-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e241-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="9e241-112">See also</span></span>

- [<span data-ttu-id="9e241-113">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9e241-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="9e241-114">ICorProfilerCallback2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9e241-114">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
