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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c1707a09f14fbab6150c2ecbcd188d7bf88064fa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59085897"
---
# <a name="cordebuggenerationtypes-enumeration"></a><span data-ttu-id="91604-102">CorDebugGenerationTypes 列挙型</span><span class="sxs-lookup"><span data-stu-id="91604-102">CorDebugGenerationTypes Enumeration</span></span>
<span data-ttu-id="91604-103">マネージド ヒープ上のメモリ領域の生成を指定します。</span><span class="sxs-lookup"><span data-stu-id="91604-103">Specifies the generation of a region of memory on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91604-104">構文</span><span class="sxs-lookup"><span data-stu-id="91604-104">Syntax</span></span>  
  
```  
typedef enum CorDebugGenerationTypes {  
    CorDebug_Gen0 = 0,  
    CorDebug_Gen1 = 1,  
    CorDebug_Gen2 = 2,  
    CorDebug_LOH  = 3,  
} CorDebugRegionTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="91604-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="91604-105">Members</span></span>  
  
|<span data-ttu-id="91604-106">メンバー名</span><span class="sxs-lookup"><span data-stu-id="91604-106">Member name</span></span>|<span data-ttu-id="91604-107">説明</span><span class="sxs-lookup"><span data-stu-id="91604-107">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebug_Gen0`|<span data-ttu-id="91604-108">ジェネレーション 0。</span><span class="sxs-lookup"><span data-stu-id="91604-108">Generation 0.</span></span>|  
|`CorDebug_Gen1`|<span data-ttu-id="91604-109">ジェネレーション 1。</span><span class="sxs-lookup"><span data-stu-id="91604-109">Generation 1.</span></span>|  
|`CorDebug_Gen2`|<span data-ttu-id="91604-110">ジェネレーション 2。</span><span class="sxs-lookup"><span data-stu-id="91604-110">Generation 2.</span></span>|  
|`CorDebug_LOH`|<span data-ttu-id="91604-111">大きなオブジェクト ヒープ。</span><span class="sxs-lookup"><span data-stu-id="91604-111">The large object heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="91604-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="91604-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91604-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="91604-113">Requirements</span></span>  
 <span data-ttu-id="91604-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="91604-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91604-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="91604-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="91604-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="91604-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="91604-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91604-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91604-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="91604-118">See also</span></span>

- [<span data-ttu-id="91604-119">列挙型のデバッグ</span><span class="sxs-lookup"><span data-stu-id="91604-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
