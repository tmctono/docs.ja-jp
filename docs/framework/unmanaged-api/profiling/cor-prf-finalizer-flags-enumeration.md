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
ms.openlocfilehash: daca2849908a7798b588ff06f6e117d412db1b33
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867270"
---
# <a name="cor_prf_finalizer_flags-enumeration"></a><span data-ttu-id="9c319-102">COR_PRF_FINALIZER_FLAGS 列挙型</span><span class="sxs-lookup"><span data-stu-id="9c319-102">COR_PRF_FINALIZER_FLAGS Enumeration</span></span>
<span data-ttu-id="9c319-103">オブジェクトのファイナライザーを記述します。</span><span class="sxs-lookup"><span data-stu-id="9c319-103">Describes the finalizer for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c319-104">構文</span><span class="sxs-lookup"><span data-stu-id="9c319-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_FINALIZER_CRITICAL = 0x1  
} COR_PRF_FINALIZER_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="9c319-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="9c319-105">Members</span></span>  
  
|<span data-ttu-id="9c319-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="9c319-106">Member</span></span>|<span data-ttu-id="9c319-107">説明</span><span class="sxs-lookup"><span data-stu-id="9c319-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FINALIZER_CRITICAL`|<span data-ttu-id="9c319-108">ファイナライザーは重要です。</span><span class="sxs-lookup"><span data-stu-id="9c319-108">The finalizer is critical.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9c319-109">コメント</span><span class="sxs-lookup"><span data-stu-id="9c319-109">Remarks</span></span>  
 <span data-ttu-id="9c319-110">`COR_PRF_FINALIZER_FLAGS` 列挙体は、 [ICorProfilerCallback2:: FinalizeableObjectQueued](icorprofilercallback2-finalizeableobjectqueued-method.md)メソッドによって、オブジェクトのファイナライザーを記述するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="9c319-110">The `COR_PRF_FINALIZER_FLAGS` enumeration is used by the [ICorProfilerCallback2::FinalizeableObjectQueued](icorprofilercallback2-finalizeableobjectqueued-method.md) method to describe the finalizer for an object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c319-111">要件</span><span class="sxs-lookup"><span data-stu-id="9c319-111">Requirements</span></span>  
 <span data-ttu-id="9c319-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c319-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c319-113">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9c319-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9c319-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9c319-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9c319-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c319-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c319-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="9c319-116">See also</span></span>

- [<span data-ttu-id="9c319-117">列挙型のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="9c319-117">Profiling Enumerations</span></span>](profiling-enumerations.md)
