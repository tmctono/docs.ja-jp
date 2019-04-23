---
title: COR_PRF_JIT_CACHE 列挙型
ms.date: 03/30/2017
api_name:
- COR_PRF_JIT_CACHE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_JIT_CACHE
helpviewer_keywords:
- COR_PRF_JIT_CACHE enumeration [.NET Framework profiling]
ms.assetid: e7b8f6b4-95bc-4ba5-b9eb-f5590a7326a4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0cdbe36403f830926d611ffdc655d82ea25ddeef
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59144795"
---
# <a name="corprfjitcache-enumeration"></a><span data-ttu-id="6a336-102">COR_PRF_JIT_CACHE 列挙型</span><span class="sxs-lookup"><span data-stu-id="6a336-102">COR_PRF_JIT_CACHE Enumeration</span></span>
<span data-ttu-id="6a336-103">キャッシュされている関数検索の結果を示します。</span><span class="sxs-lookup"><span data-stu-id="6a336-103">Indicates the result of a cached function search.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6a336-104">`COR_PRF_CACHED_FUNCTION_FOUND` そのため、0 の値を持つ`COR_PRF_JIT_CACHE`ブール サロゲートとして使用できません。</span><span class="sxs-lookup"><span data-stu-id="6a336-104">`COR_PRF_CACHED_FUNCTION_FOUND` has a value of zero, so `COR_PRF_JIT_CACHE` cannot be used as a Boolean surrogate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a336-105">構文</span><span class="sxs-lookup"><span data-stu-id="6a336-105">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_CACHED_FUNCTION_FOUND,  
    COR_PRF_CACHED_FUNCTION_NOT_FOUND  
} COR_PRF_JIT_CACHE;  
```  
  
## <a name="members"></a><span data-ttu-id="6a336-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="6a336-106">Members</span></span>  
  
|<span data-ttu-id="6a336-107">メンバー</span><span class="sxs-lookup"><span data-stu-id="6a336-107">Member</span></span>|<span data-ttu-id="6a336-108">説明</span><span class="sxs-lookup"><span data-stu-id="6a336-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FUNCTION_FOUND`|<span data-ttu-id="6a336-109">検索では、関数が見つかりました。</span><span class="sxs-lookup"><span data-stu-id="6a336-109">The search found the function.</span></span>|  
|`COR_PRF_FUNCTION_NOT_FOUND`|<span data-ttu-id="6a336-110">検索、関数が見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="6a336-110">The search did not find the function.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6a336-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="6a336-111">Requirements</span></span>  
 <span data-ttu-id="6a336-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a336-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a336-113">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6a336-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6a336-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6a336-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6a336-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a336-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a336-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="6a336-116">See also</span></span>

- [<span data-ttu-id="6a336-117">列挙型のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="6a336-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
