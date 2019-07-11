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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 731907d69f3257306c536d73112300ffd5225538
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782891"
---
# <a name="icorprofilercallbackremotingserverinvocationreturned-method"></a><span data-ttu-id="0056b-102">ICorProfilerCallback::RemotingServerInvocationReturned メソッド</span><span class="sxs-lookup"><span data-stu-id="0056b-102">ICorProfilerCallback::RemotingServerInvocationReturned Method</span></span>
<span data-ttu-id="0056b-103">プロセスで、リモート メソッド呼び出しの要求に応答におけるメソッドの呼び出しが完了したことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="0056b-103">Notifies the profiler that the process has finished invoking a method in response to a remote method invocation request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0056b-104">構文</span><span class="sxs-lookup"><span data-stu-id="0056b-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingServerInvocationReturned();  
```  
  
## <a name="requirements"></a><span data-ttu-id="0056b-105">必要条件</span><span class="sxs-lookup"><span data-stu-id="0056b-105">Requirements</span></span>  
 <span data-ttu-id="0056b-106">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0056b-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0056b-107">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0056b-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0056b-108">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0056b-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0056b-109">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0056b-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0056b-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="0056b-110">See also</span></span>

- [<span data-ttu-id="0056b-111">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0056b-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
