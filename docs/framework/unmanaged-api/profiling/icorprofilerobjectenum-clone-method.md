---
title: ICorProfilerObjectEnum::Clone メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum.Clone
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum::Clone
helpviewer_keywords:
- Clone method, ICorProfilerObjectEnum interface [.NET Framework profiling]
- ICorProfilerObjectEnum::Clone method [.NET Framework profiling]
ms.assetid: b0b2facd-5991-4f4c-932d-c4937f45cef9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 14e8086532eff5dba6883575cc2daf447a32343a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61597662"
---
# <a name="icorprofilerobjectenumclone-method"></a><span data-ttu-id="45bd1-102">ICorProfilerObjectEnum::Clone メソッド</span><span class="sxs-lookup"><span data-stu-id="45bd1-102">ICorProfilerObjectEnum::Clone Method</span></span>
<span data-ttu-id="45bd1-103">このコピーにインターフェイス ポインターを取得[ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="45bd1-103">Gets an interface pointer to a copy of this [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45bd1-104">構文</span><span class="sxs-lookup"><span data-stu-id="45bd1-104">Syntax</span></span>  
  
```  
HRESULT Clone (  
    [out] ICorProfilerObjectEnum   **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="45bd1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="45bd1-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="45bd1-106">[out]さらにこのコピーを指すインターフェイス ポインターへのポインター`ICorProfilerObjectEnum`インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="45bd1-106">[out] A pointer to the interface pointer that in turn points to the copy of this `ICorProfilerObjectEnum` interface.</span></span> <span data-ttu-id="45bd1-107">コピーは、この 1 つから個別に独自の列挙状態を保持します。</span><span class="sxs-lookup"><span data-stu-id="45bd1-107">The copy maintains its own enumeration state separately from this one.</span></span> <span data-ttu-id="45bd1-108">ただし、コピーの初期のカーソル位置では、この列挙子の現在のカーソル位置と同じになります。</span><span class="sxs-lookup"><span data-stu-id="45bd1-108">However, the copy's initial cursor position will be the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45bd1-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="45bd1-109">Requirements</span></span>  
 <span data-ttu-id="45bd1-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="45bd1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45bd1-111">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="45bd1-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="45bd1-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="45bd1-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="45bd1-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45bd1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45bd1-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="45bd1-114">See also</span></span>

- [<span data-ttu-id="45bd1-115">ICorProfilerObjectEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="45bd1-115">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)
