---
title: CorDebugGenerationTypes 列挙型
ms.date: 03/30/2017
api_name:
- CorDebugGenerationTypes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugGenerationTypes
helpviewer_keywords:
- CorDebugGenerationTypes enumeration [.NET Framework debugging]
ms.assetid: 9f25b64f-eedd-4ae5-8b0e-cfdfb9b6c5d8
topic_type:
- apiref
ms.openlocfilehash: 0443f58b79e60111756308cc4843daf86d1fc823
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795866"
---
# <a name="cordebuggenerationtypes-enumeration"></a><span data-ttu-id="871a9-102">CorDebugGenerationTypes 列挙型</span><span class="sxs-lookup"><span data-stu-id="871a9-102">CorDebugGenerationTypes Enumeration</span></span>
<span data-ttu-id="871a9-103">マネージド ヒープ上のメモリ領域の生成を指定します。</span><span class="sxs-lookup"><span data-stu-id="871a9-103">Specifies the generation of a region of memory on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="871a9-104">構文</span><span class="sxs-lookup"><span data-stu-id="871a9-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugGenerationTypes {  
    CorDebug_Gen0 = 0,  
    CorDebug_Gen1 = 1,  
    CorDebug_Gen2 = 2,  
    CorDebug_LOH  = 3,  
} CorDebugRegionTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="871a9-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="871a9-105">Members</span></span>  
  
|<span data-ttu-id="871a9-106">メンバー名</span><span class="sxs-lookup"><span data-stu-id="871a9-106">Member name</span></span>|<span data-ttu-id="871a9-107">説明</span><span class="sxs-lookup"><span data-stu-id="871a9-107">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebug_Gen0`|<span data-ttu-id="871a9-108">ジェネレーション 0。</span><span class="sxs-lookup"><span data-stu-id="871a9-108">Generation 0.</span></span>|  
|`CorDebug_Gen1`|<span data-ttu-id="871a9-109">第 1 世代。</span><span class="sxs-lookup"><span data-stu-id="871a9-109">Generation 1.</span></span>|  
|`CorDebug_Gen2`|<span data-ttu-id="871a9-110">ジェネレーション 2。</span><span class="sxs-lookup"><span data-stu-id="871a9-110">Generation 2.</span></span>|  
|`CorDebug_LOH`|<span data-ttu-id="871a9-111">大きなオブジェクトヒープ。</span><span class="sxs-lookup"><span data-stu-id="871a9-111">The large object heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="871a9-112">解説</span><span class="sxs-lookup"><span data-stu-id="871a9-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="871a9-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="871a9-113">Requirements</span></span>  
 <span data-ttu-id="871a9-114">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="871a9-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="871a9-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="871a9-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="871a9-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="871a9-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="871a9-117">**.NET Framework のバージョン:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="871a9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="871a9-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="871a9-118">See also</span></span>

- [<span data-ttu-id="871a9-119">列挙体のデバッグ</span><span class="sxs-lookup"><span data-stu-id="871a9-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
