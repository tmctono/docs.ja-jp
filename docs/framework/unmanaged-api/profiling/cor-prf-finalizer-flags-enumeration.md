---
title: COR_PRF_FINALIZER_FLAGS 列挙型
ms.date: 03/30/2017
api_name:
- COR_PRF_FINALIZER_FLAGS
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_FINALIZER_FLAGS
helpviewer_keywords:
- COR_PRF_FINALIZER_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 297d7721-3911-4f36-9e34-d9da0c33e22a
topic_type:
- apiref
ms.openlocfilehash: b273faafd7abb86ace58bb5c24473406af3ce20e
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500974"
---
# <a name="cor_prf_finalizer_flags-enumeration"></a><span data-ttu-id="71368-102">COR_PRF_FINALIZER_FLAGS 列挙型</span><span class="sxs-lookup"><span data-stu-id="71368-102">COR_PRF_FINALIZER_FLAGS Enumeration</span></span>
<span data-ttu-id="71368-103">オブジェクトのファイナライザーを記述します。</span><span class="sxs-lookup"><span data-stu-id="71368-103">Describes the finalizer for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71368-104">構文</span><span class="sxs-lookup"><span data-stu-id="71368-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_FINALIZER_CRITICAL = 0x1  
} COR_PRF_FINALIZER_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="71368-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="71368-105">Members</span></span>  
  
|<span data-ttu-id="71368-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="71368-106">Member</span></span>|<span data-ttu-id="71368-107">説明</span><span class="sxs-lookup"><span data-stu-id="71368-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FINALIZER_CRITICAL`|<span data-ttu-id="71368-108">ファイナライザーは重要です。</span><span class="sxs-lookup"><span data-stu-id="71368-108">The finalizer is critical.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71368-109">解説</span><span class="sxs-lookup"><span data-stu-id="71368-109">Remarks</span></span>  
 <span data-ttu-id="71368-110">`COR_PRF_FINALIZER_FLAGS`列挙体は、 [ICorProfilerCallback2:: FinalizeableObjectQueued](icorprofilercallback2-finalizeableobjectqueued-method.md)メソッドによって、オブジェクトのファイナライザーを記述するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="71368-110">The `COR_PRF_FINALIZER_FLAGS` enumeration is used by the [ICorProfilerCallback2::FinalizeableObjectQueued](icorprofilercallback2-finalizeableobjectqueued-method.md) method to describe the finalizer for an object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71368-111">要件</span><span class="sxs-lookup"><span data-stu-id="71368-111">Requirements</span></span>  
 <span data-ttu-id="71368-112">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71368-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71368-113">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="71368-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="71368-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="71368-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="71368-115">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71368-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71368-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="71368-116">See also</span></span>

- [<span data-ttu-id="71368-117">列挙体のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="71368-117">Profiling Enumerations</span></span>](profiling-enumerations.md)
