---
title: ICorProfilerCallback::ExceptionCLRCatcherFound メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionCLRCatcherFound
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCLRCatcherFound
helpviewer_keywords:
- ICorProfilerCallback::ExceptionCLRCatcherFound method [.NET Framework profiling]
- ExceptionCLRCatcherFound method [.NET Framework profiling]
ms.assetid: 73fe8b4b-8f9a-4ba5-a10c-b26521396a66
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 683cec06cd4c2fdef310126adc2921c858ca5687
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776026"
---
# <a name="icorprofilercallbackexceptionclrcatcherfound-method"></a><span data-ttu-id="a1958-102">ICorProfilerCallback::ExceptionCLRCatcherFound メソッド</span><span class="sxs-lookup"><span data-stu-id="a1958-102">ICorProfilerCallback::ExceptionCLRCatcherFound Method</span></span>
<span data-ttu-id="a1958-103">ときに呼び出されます、`catch`共通言語ランタイム (CLR) 自体の内部例外が検出されたをブロックします。</span><span class="sxs-lookup"><span data-stu-id="a1958-103">Called when a `catch` block for an exception is found inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="a1958-104">このメソッドは、.NET Framework version 2.0 で廃止されています。</span><span class="sxs-lookup"><span data-stu-id="a1958-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1958-105">構文</span><span class="sxs-lookup"><span data-stu-id="a1958-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCLRCatcherFound();  
```  
  
## <a name="requirements"></a><span data-ttu-id="a1958-106">必要条件</span><span class="sxs-lookup"><span data-stu-id="a1958-106">Requirements</span></span>  
 <span data-ttu-id="a1958-107">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1958-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1958-108">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a1958-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a1958-109">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a1958-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a1958-110">**.NET framework のバージョン:** 1</span><span class="sxs-lookup"><span data-stu-id="a1958-110">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1958-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="a1958-111">See also</span></span>

- [<span data-ttu-id="a1958-112">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a1958-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="a1958-113">ExceptionCLRCatcherExecute メソッド</span><span class="sxs-lookup"><span data-stu-id="a1958-113">ExceptionCLRCatcherExecute Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherexecute-method.md)
