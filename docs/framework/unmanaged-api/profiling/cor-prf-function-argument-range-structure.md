---
title: COR_PRF_FUNCTION_ARGUMENT_RANGE 構造体
ms.date: 03/30/2017
api_name:
- COR_PRF_FUNCTION_ARGUMENT_RANGE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_FUNCTION_ARGUMENT_RANGE
helpviewer_keywords:
- COR_PRF_FUNCTION_ARGUMENT_RANGE structure [.NET Framework profiling'
ms.assetid: 9f469eac-ac66-419b-8668-fe705bc1a51f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dffefedf14d5f219736e429be191021b2de7ddd2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59125594"
---
# <a name="corprffunctionargumentrange-structure"></a><span data-ttu-id="99b12-102">COR_PRF_FUNCTION_ARGUMENT_RANGE 構造体</span><span class="sxs-lookup"><span data-stu-id="99b12-102">COR_PRF_FUNCTION_ARGUMENT_RANGE Structure</span></span>
<span data-ttu-id="99b12-103">メモリに左から右方向へ連続で格納される関数の引数のブロックを表します。</span><span class="sxs-lookup"><span data-stu-id="99b12-103">Represents a block of function arguments stored contiguously in left-to-right order in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99b12-104">構文</span><span class="sxs-lookup"><span data-stu-id="99b12-104">Syntax</span></span>  
  
```  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_RANGE {  
    UINT_PTR startAddress;  
    ULONG length;  
} COR_PRF_FUNCTION_ARGUMENT_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="99b12-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="99b12-105">Members</span></span>  
  
|<span data-ttu-id="99b12-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="99b12-106">Members</span></span>|<span data-ttu-id="99b12-107">説明</span><span class="sxs-lookup"><span data-stu-id="99b12-107">Description</span></span>|  
|-------------|-----------------|  
|`startAddress`|<span data-ttu-id="99b12-108">ブロックの開始アドレス。</span><span class="sxs-lookup"><span data-stu-id="99b12-108">The starting address of the block.</span></span>|  
|`length`|<span data-ttu-id="99b12-109">連続するブロックの長さ。</span><span class="sxs-lookup"><span data-stu-id="99b12-109">The length of the contiguous block.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="99b12-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="99b12-110">Requirements</span></span>  
 <span data-ttu-id="99b12-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="99b12-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99b12-112">**ヘッダー:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="99b12-112">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="99b12-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="99b12-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="99b12-114">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="99b12-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="99b12-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="99b12-115">See also</span></span>

- [<span data-ttu-id="99b12-116">構造体のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="99b12-116">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
