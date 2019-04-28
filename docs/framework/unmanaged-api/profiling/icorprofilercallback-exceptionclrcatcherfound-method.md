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
ms.openlocfilehash: 59225677671388b4ed31f7fa440b6e502b604c63
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61597649"
---
# <a name="icorprofilercallbackexceptionclrcatcherfound-method"></a><span data-ttu-id="d9208-102">ICorProfilerCallback::ExceptionCLRCatcherFound メソッド</span><span class="sxs-lookup"><span data-stu-id="d9208-102">ICorProfilerCallback::ExceptionCLRCatcherFound Method</span></span>
<span data-ttu-id="d9208-103">ときに呼び出されます、`catch`共通言語ランタイム (CLR) 自体の内部例外が検出されたをブロックします。</span><span class="sxs-lookup"><span data-stu-id="d9208-103">Called when a `catch` block for an exception is found inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="d9208-104">このメソッドは、.NET Framework version 2.0 で廃止されています。</span><span class="sxs-lookup"><span data-stu-id="d9208-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9208-105">構文</span><span class="sxs-lookup"><span data-stu-id="d9208-105">Syntax</span></span>  
  
```  
HRESULT ExceptionCLRCatcherFound();  
```  
  
## <a name="requirements"></a><span data-ttu-id="d9208-106">必要条件</span><span class="sxs-lookup"><span data-stu-id="d9208-106">Requirements</span></span>  
 <span data-ttu-id="d9208-107">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9208-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9208-108">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d9208-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d9208-109">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d9208-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d9208-110">**.NET framework のバージョン:** 1</span><span class="sxs-lookup"><span data-stu-id="d9208-110">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9208-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="d9208-111">See also</span></span>

- [<span data-ttu-id="d9208-112">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d9208-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="d9208-113">ExceptionCLRCatcherExecute メソッド</span><span class="sxs-lookup"><span data-stu-id="d9208-113">ExceptionCLRCatcherExecute Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherexecute-method.md)
