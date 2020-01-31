---
title: ICorProfilerCallback::RemotingServerInvocationReturned メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingServerInvocationReturned
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingServerInvocationReturned
helpviewer_keywords:
- ICorProfilerCallback::RemotingServerInvocationReturned method [.NET Framework profiling]
- RemotingServerInvocationReturned method [.NET Framework profiling]
ms.assetid: a4de6805-e159-4280-99e5-3390c86166d0
topic_type:
- apiref
ms.openlocfilehash: 4b82a334d8c64dde824802fcf2a7d0ad17457af0
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866001"
---
# <a name="icorprofilercallbackremotingserverinvocationreturned-method"></a><span data-ttu-id="cd16b-102">ICorProfilerCallback::RemotingServerInvocationReturned メソッド</span><span class="sxs-lookup"><span data-stu-id="cd16b-102">ICorProfilerCallback::RemotingServerInvocationReturned Method</span></span>
<span data-ttu-id="cd16b-103">プロセスがリモートメソッド呼び出し要求に応答してメソッドの呼び出しを完了したことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="cd16b-103">Notifies the profiler that the process has finished invoking a method in response to a remote method invocation request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd16b-104">構文</span><span class="sxs-lookup"><span data-stu-id="cd16b-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingServerInvocationReturned();  
```  
  
## <a name="requirements"></a><span data-ttu-id="cd16b-105">要件</span><span class="sxs-lookup"><span data-stu-id="cd16b-105">Requirements</span></span>  
 <span data-ttu-id="cd16b-106">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd16b-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd16b-107">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cd16b-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cd16b-108">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cd16b-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cd16b-109">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd16b-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd16b-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="cd16b-110">See also</span></span>

- [<span data-ttu-id="cd16b-111">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cd16b-111">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
