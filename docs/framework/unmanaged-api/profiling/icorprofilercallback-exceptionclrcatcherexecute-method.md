---
title: ICorProfilerCallback::ExceptionCLRCatcherExecute メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionCLRCatcherExecute
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCLRCatcherExecute
helpviewer_keywords:
- ExceptionCLRCatcherExecute method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionCLRCatcherExecute method [.NET Framework profiling]
ms.assetid: aaac8f98-5cf4-42c7-b04b-556cce367e36
topic_type:
- apiref
ms.openlocfilehash: f14dff33217656c35379a214f007ccb3642ef4b1
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866456"
---
# <a name="icorprofilercallbackexceptionclrcatcherexecute-method"></a><span data-ttu-id="8bd23-102">ICorProfilerCallback::ExceptionCLRCatcherExecute メソッド</span><span class="sxs-lookup"><span data-stu-id="8bd23-102">ICorProfilerCallback::ExceptionCLRCatcherExecute Method</span></span>
<span data-ttu-id="8bd23-103">例外の `catch` ブロックが共通言語ランタイム (CLR) 自体の内部で実行されるときに呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="8bd23-103">Called when a `catch` block for an exception is executed inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="8bd23-104">このメソッドは .NET Framework バージョン2.0 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="8bd23-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bd23-105">構文</span><span class="sxs-lookup"><span data-stu-id="8bd23-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCLRCatcherExecute();  
```  
  
## <a name="requirements"></a><span data-ttu-id="8bd23-106">要件</span><span class="sxs-lookup"><span data-stu-id="8bd23-106">Requirements</span></span>  
 <span data-ttu-id="8bd23-107">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8bd23-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8bd23-108">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8bd23-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8bd23-109">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8bd23-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8bd23-110">**.NET Framework のバージョン:** 1.1、1.0</span><span class="sxs-lookup"><span data-stu-id="8bd23-110">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bd23-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="8bd23-111">See also</span></span>

- [<span data-ttu-id="8bd23-112">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8bd23-112">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="8bd23-113">ExceptionCLRCatcherFound メソッド</span><span class="sxs-lookup"><span data-stu-id="8bd23-113">ExceptionCLRCatcherFound Method</span></span>](icorprofilercallback-exceptionclrcatcherfound-method.md)
