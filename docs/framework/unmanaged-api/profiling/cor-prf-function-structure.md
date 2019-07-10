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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 57520b4a67eb164c8f8631dc4d63d32c655dafa2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753826"
---
# <a name="corprffunction-structure"></a><span data-ttu-id="02fb0-102">COR_PRF_FUNCTION 構造体</span><span class="sxs-lookup"><span data-stu-id="02fb0-102">COR_PRF_FUNCTION Structure</span></span>
<span data-ttu-id="02fb0-103">関数の一意の表記を、その関数の ID を再コンパイルされたバージョンの ID と組み合わせることによって、提供します。</span><span class="sxs-lookup"><span data-stu-id="02fb0-103">Provides a unique representation of a function by combining its ID with the ID of its recompiled version.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02fb0-104">構文</span><span class="sxs-lookup"><span data-stu-id="02fb0-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_FUNCTION {    FunctionID functionId;    ReJITID    reJitId;} COR_PRF_FUNCTION;  
```  
  
## <a name="members"></a><span data-ttu-id="02fb0-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="02fb0-105">Members</span></span>  
  
|<span data-ttu-id="02fb0-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="02fb0-106">Member</span></span>|<span data-ttu-id="02fb0-107">説明</span><span class="sxs-lookup"><span data-stu-id="02fb0-107">Description</span></span>|  
|------------|-----------------|  
|`functionId`|<span data-ttu-id="02fb0-108">関数の ID。</span><span class="sxs-lookup"><span data-stu-id="02fb0-108">The ID of the function.</span></span>|  
|`reJitId`|<span data-ttu-id="02fb0-109">再コンパイルされた関数の ID。</span><span class="sxs-lookup"><span data-stu-id="02fb0-109">The ID of the recompiled function.</span></span> <span data-ttu-id="02fb0-110">0 (ゼロ) の値は、関数の元のバージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="02fb0-110">A value of 0 (zero) represents the original version of the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02fb0-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="02fb0-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02fb0-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="02fb0-112">Requirements</span></span>  
 <span data-ttu-id="02fb0-113">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="02fb0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02fb0-114">**ヘッダー:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="02fb0-114">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="02fb0-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="02fb0-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="02fb0-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02fb0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02fb0-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="02fb0-117">See also</span></span>

- [<span data-ttu-id="02fb0-118">構造体のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="02fb0-118">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
