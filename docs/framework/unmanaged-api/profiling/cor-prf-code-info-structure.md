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
ms.openlocfilehash: eaab5b7faeac3dd0fb64f0a387f437af44e7bc12
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867309"
---
# <a name="cor_prf_code_info-structure"></a><span data-ttu-id="b42b1-102">COR_PRF_CODE_INFO 構造体</span><span class="sxs-lookup"><span data-stu-id="b42b1-102">COR_PRF_CODE_INFO Structure</span></span>
<span data-ttu-id="b42b1-103">メモリに格納されている 1 個の連続ブロックからなるネイティブ コードを表します。</span><span class="sxs-lookup"><span data-stu-id="b42b1-103">Represents one contiguous block of native code stored in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b42b1-104">構文</span><span class="sxs-lookup"><span data-stu-id="b42b1-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_CODE_INFO {  
    UINT_PTR startAddress;  
    SIZE_T size;  
} COR_PRF_CODE_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="b42b1-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="b42b1-105">Members</span></span>  
  
|<span data-ttu-id="b42b1-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="b42b1-106">Member</span></span>|<span data-ttu-id="b42b1-107">説明</span><span class="sxs-lookup"><span data-stu-id="b42b1-107">Description</span></span>|  
|------------|-----------------|  
|`startAddress`|<span data-ttu-id="b42b1-108">連続したコードブロックの開始アドレス。</span><span class="sxs-lookup"><span data-stu-id="b42b1-108">The starting address of the contiguous block of code.</span></span>|  
|`size`|<span data-ttu-id="b42b1-109">ブロックのサイズ。</span><span class="sxs-lookup"><span data-stu-id="b42b1-109">The size of the block.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b42b1-110">要件</span><span class="sxs-lookup"><span data-stu-id="b42b1-110">Requirements</span></span>  
 <span data-ttu-id="b42b1-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b42b1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b42b1-112">**ヘッダー:** Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="b42b1-112">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="b42b1-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b42b1-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b42b1-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b42b1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b42b1-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="b42b1-115">See also</span></span>

- [<span data-ttu-id="b42b1-116">構造体のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="b42b1-116">Profiling Structures</span></span>](profiling-structures.md)
