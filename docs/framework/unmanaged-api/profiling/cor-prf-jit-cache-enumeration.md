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
ms.openlocfilehash: d19d7ed2262db6d3c6e7f15db0e96da52f86db4a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500859"
---
# <a name="cor_prf_jit_cache-enumeration"></a><span data-ttu-id="0185a-102">COR_PRF_JIT_CACHE 列挙型</span><span class="sxs-lookup"><span data-stu-id="0185a-102">COR_PRF_JIT_CACHE Enumeration</span></span>
<span data-ttu-id="0185a-103">キャッシュされている関数検索の結果を示します。</span><span class="sxs-lookup"><span data-stu-id="0185a-103">Indicates the result of a cached function search.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0185a-104">`COR_PRF_CACHED_FUNCTION_FOUND`の値は0であるため、 `COR_PRF_JIT_CACHE` ブールサロゲートとして使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="0185a-104">`COR_PRF_CACHED_FUNCTION_FOUND` has a value of zero, so `COR_PRF_JIT_CACHE` cannot be used as a Boolean surrogate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0185a-105">構文</span><span class="sxs-lookup"><span data-stu-id="0185a-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_CACHED_FUNCTION_FOUND,  
    COR_PRF_CACHED_FUNCTION_NOT_FOUND  
} COR_PRF_JIT_CACHE;  
```  
  
## <a name="members"></a><span data-ttu-id="0185a-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="0185a-106">Members</span></span>  
  
|<span data-ttu-id="0185a-107">メンバー</span><span class="sxs-lookup"><span data-stu-id="0185a-107">Member</span></span>|<span data-ttu-id="0185a-108">説明</span><span class="sxs-lookup"><span data-stu-id="0185a-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FUNCTION_FOUND`|<span data-ttu-id="0185a-109">検索によって関数が検出されました。</span><span class="sxs-lookup"><span data-stu-id="0185a-109">The search found the function.</span></span>|  
|`COR_PRF_FUNCTION_NOT_FOUND`|<span data-ttu-id="0185a-110">検索で関数が見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="0185a-110">The search did not find the function.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0185a-111">要件</span><span class="sxs-lookup"><span data-stu-id="0185a-111">Requirements</span></span>  
 <span data-ttu-id="0185a-112">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0185a-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0185a-113">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0185a-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0185a-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0185a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0185a-115">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0185a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0185a-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="0185a-116">See also</span></span>

- [<span data-ttu-id="0185a-117">列挙体のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="0185a-117">Profiling Enumerations</span></span>](profiling-enumerations.md)
