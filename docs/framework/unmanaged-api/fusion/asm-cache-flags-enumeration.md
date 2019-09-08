---
title: ASM_CACHE_FLAGS 列挙型
ms.date: 03/30/2017
api_name:
- ASM_CACHE_FLAGS
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- ASM_CACHE_FLAGS
helpviewer_keywords:
- ASM_CACHE_FLAGS enumeration [.NET Framework fusion]
ms.assetid: 82e9a7da-321b-48b8-b239-52eaffda6be8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0e3e9da3db71d3e24b2a60ff032a631680055b88
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795274"
---
# <a name="asm_cache_flags-enumeration"></a><span data-ttu-id="91e1d-102">ASM_CACHE_FLAGS 列挙型</span><span class="sxs-lookup"><span data-stu-id="91e1d-102">ASM_CACHE_FLAGS Enumeration</span></span>
<span data-ttu-id="91e1d-103">グローバルアセンブリキャッシュ内の[Iassemblycacheitem](iassemblycacheitem-interface.md)によって表されるアセンブリのソースを示します。</span><span class="sxs-lookup"><span data-stu-id="91e1d-103">Indicates the source of an assembly that is represented by [IAssemblyCacheItem](iassemblycacheitem-interface.md) in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91e1d-104">構文</span><span class="sxs-lookup"><span data-stu-id="91e1d-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    ASM_CACHE_ZAP       = 0x01,  
    ASM_CACHE_GAC       = 0x02,  
    ASM_CACHE_DOWNLOAD  = 0x04,  
    ASM_CACHE_ROOT      = 0x08,  
    ASM_CACHE_ROOT_EX   = 0x80  
} ASM_CACHE_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="91e1d-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="91e1d-105">Members</span></span>  
  
|<span data-ttu-id="91e1d-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="91e1d-106">Member</span></span>|<span data-ttu-id="91e1d-107">説明</span><span class="sxs-lookup"><span data-stu-id="91e1d-107">Description</span></span>|  
|------------|-----------------|  
|`ASM_CACHE_ZAP`|<span data-ttu-id="91e1d-108">Ngen.exe を使用して、プリコンパイル済みアセンブリのキャッシュを列挙します。</span><span class="sxs-lookup"><span data-stu-id="91e1d-108">Enumerates the cache of precompiled assemblies by using Ngen.exe.</span></span>|  
|`ASM_CACHE_GAC`|<span data-ttu-id="91e1d-109">グローバルアセンブリキャッシュを列挙します。</span><span class="sxs-lookup"><span data-stu-id="91e1d-109">Enumerates the global assembly cache.</span></span>|  
|`ASM_CACHE_DOWNLOAD`|<span data-ttu-id="91e1d-110">要求時にダウンロードされた、またはシャドウコピーされたアセンブリを列挙します。</span><span class="sxs-lookup"><span data-stu-id="91e1d-110">Enumerates the assemblies that have been downloaded on demand or that have been shadow-copied.</span></span>|  
|`ASM_CACHE_ROOT`|<span data-ttu-id="91e1d-111">[Getcachepath](getcachepath-function.md)関数が、共通言語ランタイム (CLR) バージョン2.0 のグローバルアセンブリキャッシュへのパスを返す必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="91e1d-111">Indicates that the [GetCachePath](getcachepath-function.md) function should return the path to the global assembly cache for the common language runtime (CLR) version 2.0.</span></span> <span data-ttu-id="91e1d-112">[Getcachepath](getcachepath-function.md)への呼び出しのコンテキストでのみ意味があります。</span><span class="sxs-lookup"><span data-stu-id="91e1d-112">Meaningful only in the context of a call to [GetCachePath](getcachepath-function.md).</span></span>|  
|`ASM_CACHE_ROOT_EX`|<span data-ttu-id="91e1d-113">[Getcachepath](getcachepath-function.md)関数が CLR version 4 のグローバルアセンブリキャッシュへのパスを返す必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="91e1d-113">Indicates that the [GetCachePath](getcachepath-function.md) function should return the path to the global assembly cache for CLR version 4.</span></span> <span data-ttu-id="91e1d-114">[Getcachepath](getcachepath-function.md)への呼び出しのコンテキストでのみ意味があります。</span><span class="sxs-lookup"><span data-stu-id="91e1d-114">Meaningful only in the context of a call to [GetCachePath](getcachepath-function.md).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="91e1d-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="91e1d-115">Requirements</span></span>  
 <span data-ttu-id="91e1d-116">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="91e1d-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91e1d-117">**ヘッダー:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="91e1d-117">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="91e1d-118">**ライブラリ**Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="91e1d-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="91e1d-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91e1d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91e1d-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="91e1d-120">See also</span></span>

- [<span data-ttu-id="91e1d-121">GetCachePath 関数</span><span class="sxs-lookup"><span data-stu-id="91e1d-121">GetCachePath Function</span></span>](getcachepath-function.md)
- [<span data-ttu-id="91e1d-122">IAssemblyCacheItem インターフェイス</span><span class="sxs-lookup"><span data-stu-id="91e1d-122">IAssemblyCacheItem Interface</span></span>](iassemblycacheitem-interface.md)
- [<span data-ttu-id="91e1d-123">Fusion 列挙型</span><span class="sxs-lookup"><span data-stu-id="91e1d-123">Fusion Enumerations</span></span>](fusion-enumerations.md)
