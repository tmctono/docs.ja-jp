---
title: COR_PRF_CODE_INFO 構造体
ms.date: 03/30/2017
api_name:
- COR_PRF_CODE_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_CODE_INFO
helpviewer_keywords:
- COR_PRF_CODE_INFO structure [.NET Framework profiling]
ms.assetid: cf30e27c-1f7e-43a2-ba1e-01e4137301db
topic_type:
- apiref
ms.openlocfilehash: 643c9d7104c374d9141a604083f3fdcd540156c4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428391"
---
# <a name="cor_prf_code_info-structure"></a><span data-ttu-id="d0d3f-102">COR_PRF_CODE_INFO 構造体</span><span class="sxs-lookup"><span data-stu-id="d0d3f-102">COR_PRF_CODE_INFO Structure</span></span>
<span data-ttu-id="d0d3f-103">メモリに格納されている 1 個の連続ブロックからなるネイティブ コードを表します。</span><span class="sxs-lookup"><span data-stu-id="d0d3f-103">Represents one contiguous block of native code stored in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0d3f-104">構文</span><span class="sxs-lookup"><span data-stu-id="d0d3f-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_CODE_INFO {  
    UINT_PTR startAddress;  
    SIZE_T size;  
} COR_PRF_CODE_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="d0d3f-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="d0d3f-105">Members</span></span>  
  
|<span data-ttu-id="d0d3f-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="d0d3f-106">Member</span></span>|<span data-ttu-id="d0d3f-107">説明</span><span class="sxs-lookup"><span data-stu-id="d0d3f-107">Description</span></span>|  
|------------|-----------------|  
|`startAddress`|<span data-ttu-id="d0d3f-108">The starting address of the contiguous block of code.</span><span class="sxs-lookup"><span data-stu-id="d0d3f-108">The starting address of the contiguous block of code.</span></span>|  
|`size`|<span data-ttu-id="d0d3f-109">The size of the block.</span><span class="sxs-lookup"><span data-stu-id="d0d3f-109">The size of the block.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d0d3f-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="d0d3f-110">Requirements</span></span>  
 <span data-ttu-id="d0d3f-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0d3f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0d3f-112">**Header:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="d0d3f-112">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="d0d3f-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d0d3f-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d0d3f-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0d3f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0d3f-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="d0d3f-115">See also</span></span>

- [<span data-ttu-id="d0d3f-116">構造体のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="d0d3f-116">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
