---
title: COR_PRF_GC_ROOT_KIND 列挙型
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_ROOT_KIND
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_ROOT_KIND
helpviewer_keywords:
- COR_PRF_GC_ROOT_KIND enumeration [.NET Framework profiling]
ms.assetid: b9fb1c03-417f-41d4-aed4-02cb4ade8def
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4b7a4c8dfc9e082b29d462b835886d6bf252bb39
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753666"
---
# <a name="corprfgcrootkind-enumeration"></a><span data-ttu-id="a7f20-102">COR_PRF_GC_ROOT_KIND 列挙型</span><span class="sxs-lookup"><span data-stu-id="a7f20-102">COR_PRF_GC_ROOT_KIND Enumeration</span></span>
<span data-ttu-id="a7f20-103">によって公開されるガベージ コレクションのルートの種類を示す、 [icorprofilercallback 2::rootreferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md)コールバック。</span><span class="sxs-lookup"><span data-stu-id="a7f20-103">Indicates the kind of garbage collection root that is exposed by the [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7f20-104">構文</span><span class="sxs-lookup"><span data-stu-id="a7f20-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_GC_ROOT_STACK = 1,  
    COR_PRF_GC_ROOT_FINALIZER = 2,  
    COR_PRF_GC_ROOT_HANDLE = 3,  
    COR_PRF_GC_ROOT_OTHER = 0  
} COR_PRF_GC_ROOT_KIND;  
```  
  
## <a name="members"></a><span data-ttu-id="a7f20-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="a7f20-105">Members</span></span>  
  
|<span data-ttu-id="a7f20-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="a7f20-106">Member</span></span>|<span data-ttu-id="a7f20-107">説明</span><span class="sxs-lookup"><span data-stu-id="a7f20-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_STACK`|<span data-ttu-id="a7f20-108">ルートは、スタック上の変数です。</span><span class="sxs-lookup"><span data-stu-id="a7f20-108">The root is a variable on the stack.</span></span>|  
|`COR_PRF_GC_ROOT_FINALIZER`|<span data-ttu-id="a7f20-109">ルートは、ファイナライザー キュー内のエントリです。</span><span class="sxs-lookup"><span data-stu-id="a7f20-109">The root is an entry in the finalizer queue.</span></span>|  
|`COR_PRF_GC_ROOT_HANDLE`|<span data-ttu-id="a7f20-110">ルートは、ガベージ コレクション ハンドルです。</span><span class="sxs-lookup"><span data-stu-id="a7f20-110">The root is a garbage collection handle.</span></span>|  
|`COR_PRF_GC_ROOT_OTHER`|<span data-ttu-id="a7f20-111">ルートの種類が指定されていません。</span><span class="sxs-lookup"><span data-stu-id="a7f20-111">The kind of root is unspecified.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a7f20-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="a7f20-112">Requirements</span></span>  
 <span data-ttu-id="a7f20-113">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7f20-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7f20-114">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a7f20-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a7f20-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7f20-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a7f20-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7f20-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7f20-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="a7f20-117">See also</span></span>

- [<span data-ttu-id="a7f20-118">列挙型のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="a7f20-118">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
