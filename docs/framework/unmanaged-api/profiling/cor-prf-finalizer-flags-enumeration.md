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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a66b2b94765c3d59327e500f1e208dc93cd8e231
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781931"
---
# <a name="corprffinalizerflags-enumeration"></a><span data-ttu-id="d9afc-102">COR_PRF_FINALIZER_FLAGS 列挙型</span><span class="sxs-lookup"><span data-stu-id="d9afc-102">COR_PRF_FINALIZER_FLAGS Enumeration</span></span>
<span data-ttu-id="d9afc-103">オブジェクトのファイナライザーを記述します。</span><span class="sxs-lookup"><span data-stu-id="d9afc-103">Describes the finalizer for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9afc-104">構文</span><span class="sxs-lookup"><span data-stu-id="d9afc-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_FINALIZER_CRITICAL = 0x1  
} COR_PRF_FINALIZER_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="d9afc-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="d9afc-105">Members</span></span>  
  
|<span data-ttu-id="d9afc-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="d9afc-106">Member</span></span>|<span data-ttu-id="d9afc-107">説明</span><span class="sxs-lookup"><span data-stu-id="d9afc-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FINALIZER_CRITICAL`|<span data-ttu-id="d9afc-108">ファイナライザーが重要です。</span><span class="sxs-lookup"><span data-stu-id="d9afc-108">The finalizer is critical.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d9afc-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="d9afc-109">Remarks</span></span>  
 <span data-ttu-id="d9afc-110">`COR_PRF_FINALIZER_FLAGS`列挙型を使用して、 [icorprofilercallback 2::finalizeableobjectqueued](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md)オブジェクトのファイナライザーを記述するメソッド。</span><span class="sxs-lookup"><span data-stu-id="d9afc-110">The `COR_PRF_FINALIZER_FLAGS` enumeration is used by the [ICorProfilerCallback2::FinalizeableObjectQueued](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md) method to describe the finalizer for an object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9afc-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="d9afc-111">Requirements</span></span>  
 <span data-ttu-id="d9afc-112">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9afc-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9afc-113">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d9afc-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d9afc-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d9afc-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d9afc-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9afc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9afc-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="d9afc-116">See also</span></span>

- [<span data-ttu-id="d9afc-117">列挙型のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="d9afc-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
