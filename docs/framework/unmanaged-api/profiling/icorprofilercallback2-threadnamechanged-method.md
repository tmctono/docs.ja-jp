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
ms.openlocfilehash: c5182fd44f0cc2ad7b836bbcbddc469c89dbacb7
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865702"
---
# <a name="icorprofilercallback2threadnamechanged-method"></a><span data-ttu-id="dbb18-102">ICorProfilerCallback2::ThreadNameChanged メソッド</span><span class="sxs-lookup"><span data-stu-id="dbb18-102">ICorProfilerCallback2::ThreadNameChanged Method</span></span>
<span data-ttu-id="dbb18-103">スレッドの名前が変更されたことをコードプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="dbb18-103">Notifies the code profiler that the name of a thread has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbb18-104">構文</span><span class="sxs-lookup"><span data-stu-id="dbb18-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadNameChanged(  
    [in] ThreadID threadId,  
    [in] ULONG cchName,  
    [in] WCHAR name[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dbb18-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dbb18-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="dbb18-106">からスレッドの ID。</span><span class="sxs-lookup"><span data-stu-id="dbb18-106">[in] The ID of the thread.</span></span>  
  
 `cchName`  
 <span data-ttu-id="dbb18-107">からスレッドの新しい名前の長さ。</span><span class="sxs-lookup"><span data-stu-id="dbb18-107">[in] The length of the new name of the thread.</span></span>  
  
 `name`  
 <span data-ttu-id="dbb18-108">からスレッドの新しい名前。</span><span class="sxs-lookup"><span data-stu-id="dbb18-108">[in] The new name of the thread.</span></span> <span data-ttu-id="dbb18-109">名前が null で終了していません。</span><span class="sxs-lookup"><span data-stu-id="dbb18-109">The name is not null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dbb18-110">要件</span><span class="sxs-lookup"><span data-stu-id="dbb18-110">Requirements</span></span>  
 <span data-ttu-id="dbb18-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbb18-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dbb18-112">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="dbb18-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="dbb18-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dbb18-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dbb18-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dbb18-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbb18-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="dbb18-115">See also</span></span>

- [<span data-ttu-id="dbb18-116">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dbb18-116">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="dbb18-117">ICorProfilerCallback2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dbb18-117">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
