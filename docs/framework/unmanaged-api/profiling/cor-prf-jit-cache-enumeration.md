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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59144795"
---
# <a name="corprfjitcache-enumeration"></a><span data-ttu-id="46d35-102">COR_PRF_JIT_CACHE 列挙型</span><span class="sxs-lookup"><span data-stu-id="46d35-102">COR_PRF_JIT_CACHE Enumeration</span></span>
<span data-ttu-id="46d35-103">キャッシュされている関数検索の結果を示します。</span><span class="sxs-lookup"><span data-stu-id="46d35-103">Indicates the result of a cached function search.</span></span>  
  
> [!NOTE]
>  `COR_PRF_CACHED_FUNCTION_FOUND` <span data-ttu-id="46d35-104">そのため、0 の値を持つ`COR_PRF_JIT_CACHE`ブール サロゲートとして使用できません。</span><span class="sxs-lookup"><span data-stu-id="46d35-104">has a value of zero, so `COR_PRF_JIT_CACHE` cannot be used as a Boolean surrogate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46d35-105">構文</span><span class="sxs-lookup"><span data-stu-id="46d35-105">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_CACHED_FUNCTION_FOUND,  
    COR_PRF_CACHED_FUNCTION_NOT_FOUND  
} COR_PRF_JIT_CACHE;  
```  
  
## <a name="members"></a><span data-ttu-id="46d35-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="46d35-106">Members</span></span>  
  
|<span data-ttu-id="46d35-107">メンバー</span><span class="sxs-lookup"><span data-stu-id="46d35-107">Member</span></span>|<span data-ttu-id="46d35-108">説明</span><span class="sxs-lookup"><span data-stu-id="46d35-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FUNCTION_FOUND`|<span data-ttu-id="46d35-109">検索では、関数が見つかりました。</span><span class="sxs-lookup"><span data-stu-id="46d35-109">The search found the function.</span></span>|  
|`COR_PRF_FUNCTION_NOT_FOUND`|<span data-ttu-id="46d35-110">検索、関数が見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="46d35-110">The search did not find the function.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="46d35-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="46d35-111">Requirements</span></span>  
 <span data-ttu-id="46d35-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="46d35-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46d35-113">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="46d35-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="46d35-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="46d35-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="46d35-115">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="46d35-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="46d35-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="46d35-116">See also</span></span>

- [<span data-ttu-id="46d35-117">列挙体のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="46d35-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
