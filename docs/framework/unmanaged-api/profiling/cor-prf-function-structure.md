---
title: COR_PRF_FUNCTION 構造体
ms.date: 03/30/2017
api_name:
- COR_PRF_FUNCTION
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_FUNCTION
helpviewer_keywords:
- COR_PRF_FUNCTION structure [.NET Framework profiling]
ms.assetid: 8bb5acf5-cf4b-4ccb-93f1-46db1f3f8bf3
topic_type:
- apiref
ms.openlocfilehash: 40698a49ac7012c4f67eb88b1ead04c80f3dea77
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428320"
---
# <a name="cor_prf_function-structure"></a><span data-ttu-id="fa269-102">COR_PRF_FUNCTION 構造体</span><span class="sxs-lookup"><span data-stu-id="fa269-102">COR_PRF_FUNCTION Structure</span></span>
<span data-ttu-id="fa269-103">関数の一意の表記を、その関数の ID を再コンパイルされたバージョンの ID と組み合わせることによって、提供します。</span><span class="sxs-lookup"><span data-stu-id="fa269-103">Provides a unique representation of a function by combining its ID with the ID of its recompiled version.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa269-104">構文</span><span class="sxs-lookup"><span data-stu-id="fa269-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_FUNCTION {    FunctionID functionId;    ReJITID    reJitId;} COR_PRF_FUNCTION;  
```  
  
## <a name="members"></a><span data-ttu-id="fa269-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="fa269-105">Members</span></span>  
  
|<span data-ttu-id="fa269-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="fa269-106">Member</span></span>|<span data-ttu-id="fa269-107">説明</span><span class="sxs-lookup"><span data-stu-id="fa269-107">Description</span></span>|  
|------------|-----------------|  
|`functionId`|<span data-ttu-id="fa269-108">関数の ID。</span><span class="sxs-lookup"><span data-stu-id="fa269-108">The ID of the function.</span></span>|  
|`reJitId`|<span data-ttu-id="fa269-109">再コンパイルされた関数の ID。</span><span class="sxs-lookup"><span data-stu-id="fa269-109">The ID of the recompiled function.</span></span> <span data-ttu-id="fa269-110">0 (ゼロ) の値は、関数の元のバージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="fa269-110">A value of 0 (zero) represents the original version of the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa269-111">コメント</span><span class="sxs-lookup"><span data-stu-id="fa269-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa269-112">要件</span><span class="sxs-lookup"><span data-stu-id="fa269-112">Requirements</span></span>  
 <span data-ttu-id="fa269-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa269-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa269-114">**ヘッダー:** Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="fa269-114">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="fa269-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fa269-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fa269-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa269-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa269-117">参照</span><span class="sxs-lookup"><span data-stu-id="fa269-117">See also</span></span>

- [<span data-ttu-id="fa269-118">構造体のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="fa269-118">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
