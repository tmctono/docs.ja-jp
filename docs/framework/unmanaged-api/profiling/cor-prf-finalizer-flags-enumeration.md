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
ms.openlocfilehash: d5037f335e8d66c341d70d91d955a1ac7571b823
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775148"
---
# <a name="corprffinalizerflags-enumeration"></a><span data-ttu-id="6f989-102">COR_PRF_FINALIZER_FLAGS 列挙型</span><span class="sxs-lookup"><span data-stu-id="6f989-102">COR_PRF_FINALIZER_FLAGS Enumeration</span></span>
<span data-ttu-id="6f989-103">オブジェクトのファイナライザーを記述します。</span><span class="sxs-lookup"><span data-stu-id="6f989-103">Describes the finalizer for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f989-104">構文</span><span class="sxs-lookup"><span data-stu-id="6f989-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_FINALIZER_CRITICAL = 0x1  
} COR_PRF_FINALIZER_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="6f989-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="6f989-105">Members</span></span>  
  
|<span data-ttu-id="6f989-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="6f989-106">Member</span></span>|<span data-ttu-id="6f989-107">説明</span><span class="sxs-lookup"><span data-stu-id="6f989-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FINALIZER_CRITICAL`|<span data-ttu-id="6f989-108">ファイナライザーが重要です。</span><span class="sxs-lookup"><span data-stu-id="6f989-108">The finalizer is critical.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6f989-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="6f989-109">Remarks</span></span>  
 <span data-ttu-id="6f989-110">`COR_PRF_FINALIZER_FLAGS`列挙型を使用して、 [icorprofilercallback 2::finalizeableobjectqueued](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md)オブジェクトのファイナライザーを記述するメソッド。</span><span class="sxs-lookup"><span data-stu-id="6f989-110">The `COR_PRF_FINALIZER_FLAGS` enumeration is used by the [ICorProfilerCallback2::FinalizeableObjectQueued](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md) method to describe the finalizer for an object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f989-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="6f989-111">Requirements</span></span>  
 <span data-ttu-id="6f989-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f989-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f989-113">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6f989-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6f989-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6f989-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6f989-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f989-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f989-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="6f989-116">See also</span></span>

- [<span data-ttu-id="6f989-117">列挙型のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="6f989-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
