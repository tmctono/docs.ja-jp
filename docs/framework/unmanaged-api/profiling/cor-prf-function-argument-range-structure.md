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
ms.openlocfilehash: c0c0679dac84089577a2698ed8b0b5497a1a81e8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753906"
---
# <a name="corprffunctionargumentrange-structure"></a><span data-ttu-id="cba5b-102">COR_PRF_FUNCTION_ARGUMENT_RANGE 構造体</span><span class="sxs-lookup"><span data-stu-id="cba5b-102">COR_PRF_FUNCTION_ARGUMENT_RANGE Structure</span></span>
<span data-ttu-id="cba5b-103">メモリに左から右方向へ連続で格納される関数の引数のブロックを表します。</span><span class="sxs-lookup"><span data-stu-id="cba5b-103">Represents a block of function arguments stored contiguously in left-to-right order in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cba5b-104">構文</span><span class="sxs-lookup"><span data-stu-id="cba5b-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_RANGE {  
    UINT_PTR startAddress;  
    ULONG length;  
} COR_PRF_FUNCTION_ARGUMENT_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="cba5b-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="cba5b-105">Members</span></span>  
  
|<span data-ttu-id="cba5b-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="cba5b-106">Members</span></span>|<span data-ttu-id="cba5b-107">説明</span><span class="sxs-lookup"><span data-stu-id="cba5b-107">Description</span></span>|  
|-------------|-----------------|  
|`startAddress`|<span data-ttu-id="cba5b-108">ブロックの開始アドレス。</span><span class="sxs-lookup"><span data-stu-id="cba5b-108">The starting address of the block.</span></span>|  
|`length`|<span data-ttu-id="cba5b-109">連続するブロックの長さ。</span><span class="sxs-lookup"><span data-stu-id="cba5b-109">The length of the contiguous block.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cba5b-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="cba5b-110">Requirements</span></span>  
 <span data-ttu-id="cba5b-111">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cba5b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cba5b-112">**ヘッダー:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="cba5b-112">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="cba5b-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cba5b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cba5b-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cba5b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cba5b-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="cba5b-115">See also</span></span>

- [<span data-ttu-id="cba5b-116">構造体のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="cba5b-116">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
