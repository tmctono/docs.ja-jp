---
title: ICorProfilerCallback::RemotingServerInvocationStarted メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingServerInvocationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingServerInvocationStarted
helpviewer_keywords:
- RemotingServerInvocationStarted method [.NET Framework profiling]
- ICorProfilerCallback::RemotingServerInvocationStarted method [.NET Framework profiling]
ms.assetid: 86051a11-ad8e-4ace-9a11-ff0f982a5e11
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 83c9a4aa165057f1345de2c6f5bda80e4317d06c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59221809"
---
# <a name="icorprofilercallbackremotingserverinvocationstarted-method"></a><span data-ttu-id="7c141-102">ICorProfilerCallback::RemotingServerInvocationStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="7c141-102">ICorProfilerCallback::RemotingServerInvocationStarted Method</span></span>
<span data-ttu-id="7c141-103">プロセスがリモート メソッド呼び出しの要求に応答でメソッドを呼び出すことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="7c141-103">Notifies the profiler that the process is invoking a method in response to a remote method invocation request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c141-104">構文</span><span class="sxs-lookup"><span data-stu-id="7c141-104">Syntax</span></span>  
  
```  
HRESULT RemotingServerInvocationStarted();  
```  
  
## <a name="requirements"></a><span data-ttu-id="7c141-105">必要条件</span><span class="sxs-lookup"><span data-stu-id="7c141-105">Requirements</span></span>  
 <span data-ttu-id="7c141-106">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c141-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c141-107">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7c141-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7c141-108">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c141-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7c141-109">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c141-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c141-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="7c141-110">See also</span></span>

- [<span data-ttu-id="7c141-111">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7c141-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
