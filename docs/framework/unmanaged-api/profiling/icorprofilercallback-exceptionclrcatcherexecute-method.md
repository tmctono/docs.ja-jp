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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b640a6dee9ae50278d6a844d20d21eae156e9dd7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59200963"
---
# <a name="icorprofilercallbackexceptionclrcatcherexecute-method"></a><span data-ttu-id="28548-102">ICorProfilerCallback::ExceptionCLRCatcherExecute メソッド</span><span class="sxs-lookup"><span data-stu-id="28548-102">ICorProfilerCallback::ExceptionCLRCatcherExecute Method</span></span>
<span data-ttu-id="28548-103">ときに呼び出されます、`catch`共通言語ランタイム (CLR) 自体の内部例外が実行されるをブロックします。</span><span class="sxs-lookup"><span data-stu-id="28548-103">Called when a `catch` block for an exception is executed inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="28548-104">このメソッドは、.NET Framework version 2.0 で廃止されています。</span><span class="sxs-lookup"><span data-stu-id="28548-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28548-105">構文</span><span class="sxs-lookup"><span data-stu-id="28548-105">Syntax</span></span>  
  
```  
HRESULT ExceptionCLRCatcherExecute();  
```  
  
## <a name="requirements"></a><span data-ttu-id="28548-106">必要条件</span><span class="sxs-lookup"><span data-stu-id="28548-106">Requirements</span></span>  
 <span data-ttu-id="28548-107">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="28548-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28548-108">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="28548-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="28548-109">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="28548-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="28548-110">**.NET framework のバージョン:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="28548-110">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28548-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="28548-111">See also</span></span>

- [<span data-ttu-id="28548-112">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="28548-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="28548-113">ExceptionCLRCatcherFound メソッド</span><span class="sxs-lookup"><span data-stu-id="28548-113">ExceptionCLRCatcherFound Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherfound-method.md)
