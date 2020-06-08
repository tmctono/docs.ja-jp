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
ms.openlocfilehash: b79c8dd9f27805e00535dde53c6ee9f5ee457b42
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500264"
---
# <a name="icorprofilercallbackexceptionclrcatcherexecute-method"></a><span data-ttu-id="02407-102">ICorProfilerCallback::ExceptionCLRCatcherExecute メソッド</span><span class="sxs-lookup"><span data-stu-id="02407-102">ICorProfilerCallback::ExceptionCLRCatcherExecute Method</span></span>
<span data-ttu-id="02407-103">`catch`例外のブロックが共通言語ランタイム (CLR) 自体の内部で実行されるときに呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="02407-103">Called when a `catch` block for an exception is executed inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="02407-104">このメソッドは .NET Framework バージョン2.0 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="02407-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02407-105">構文</span><span class="sxs-lookup"><span data-stu-id="02407-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCLRCatcherExecute();  
```  
  
## <a name="requirements"></a><span data-ttu-id="02407-106">要件</span><span class="sxs-lookup"><span data-stu-id="02407-106">Requirements</span></span>  
 <span data-ttu-id="02407-107">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02407-107">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02407-108">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="02407-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="02407-109">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="02407-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="02407-110">**.NET Framework のバージョン:** 1.1、1.0</span><span class="sxs-lookup"><span data-stu-id="02407-110">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02407-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="02407-111">See also</span></span>

- [<span data-ttu-id="02407-112">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="02407-112">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="02407-113">ExceptionCLRCatcherFound メソッド</span><span class="sxs-lookup"><span data-stu-id="02407-113">ExceptionCLRCatcherFound Method</span></span>](icorprofilercallback-exceptionclrcatcherfound-method.md)
