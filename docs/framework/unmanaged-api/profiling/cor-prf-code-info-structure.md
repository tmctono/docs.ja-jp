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
ms.openlocfilehash: 9dbe0219f5932a9d212edaf5181b96335c47db0e
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501015"
---
# <a name="cor_prf_code_info-structure"></a><span data-ttu-id="4774b-102">COR_PRF_CODE_INFO 構造体</span><span class="sxs-lookup"><span data-stu-id="4774b-102">COR_PRF_CODE_INFO Structure</span></span>
<span data-ttu-id="4774b-103">メモリに格納されている 1 個の連続ブロックからなるネイティブ コードを表します。</span><span class="sxs-lookup"><span data-stu-id="4774b-103">Represents one contiguous block of native code stored in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4774b-104">構文</span><span class="sxs-lookup"><span data-stu-id="4774b-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_CODE_INFO {  
    UINT_PTR startAddress;  
    SIZE_T size;  
} COR_PRF_CODE_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="4774b-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="4774b-105">Members</span></span>  
  
|<span data-ttu-id="4774b-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="4774b-106">Member</span></span>|<span data-ttu-id="4774b-107">説明</span><span class="sxs-lookup"><span data-stu-id="4774b-107">Description</span></span>|  
|------------|-----------------|  
|`startAddress`|<span data-ttu-id="4774b-108">連続したコードブロックの開始アドレス。</span><span class="sxs-lookup"><span data-stu-id="4774b-108">The starting address of the contiguous block of code.</span></span>|  
|`size`|<span data-ttu-id="4774b-109">ブロックのサイズ。</span><span class="sxs-lookup"><span data-stu-id="4774b-109">The size of the block.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4774b-110">要件</span><span class="sxs-lookup"><span data-stu-id="4774b-110">Requirements</span></span>  
 <span data-ttu-id="4774b-111">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4774b-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4774b-112">**ヘッダー:** Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="4774b-112">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="4774b-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4774b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4774b-114">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4774b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4774b-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="4774b-115">See also</span></span>

- [<span data-ttu-id="4774b-116">構造体のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="4774b-116">Profiling Structures</span></span>](profiling-structures.md)
