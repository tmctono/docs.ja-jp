---
title: CorDebugGenerationTypes 列挙体
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
ms.openlocfilehash: 6133b34a60fd06c1b75d69783760741b8de62071
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789340"
---
# <a name="cordebuggenerationtypes-enumeration"></a><span data-ttu-id="51142-102">CorDebugGenerationTypes 列挙体</span><span class="sxs-lookup"><span data-stu-id="51142-102">CorDebugGenerationTypes Enumeration</span></span>
<span data-ttu-id="51142-103">マネージド ヒープ上のメモリ領域の生成を指定します。</span><span class="sxs-lookup"><span data-stu-id="51142-103">Specifies the generation of a region of memory on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51142-104">構文</span><span class="sxs-lookup"><span data-stu-id="51142-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugGenerationTypes {  
    CorDebug_Gen0 = 0,  
    CorDebug_Gen1 = 1,  
    CorDebug_Gen2 = 2,  
    CorDebug_LOH  = 3,  
} CorDebugRegionTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="51142-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="51142-105">Members</span></span>  
  
|<span data-ttu-id="51142-106">メンバー名</span><span class="sxs-lookup"><span data-stu-id="51142-106">Member name</span></span>|<span data-ttu-id="51142-107">説明</span><span class="sxs-lookup"><span data-stu-id="51142-107">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebug_Gen0`|<span data-ttu-id="51142-108">ジェネレーション 0。</span><span class="sxs-lookup"><span data-stu-id="51142-108">Generation 0.</span></span>|  
|`CorDebug_Gen1`|<span data-ttu-id="51142-109">ジェネレーション 1。</span><span class="sxs-lookup"><span data-stu-id="51142-109">Generation 1.</span></span>|  
|`CorDebug_Gen2`|<span data-ttu-id="51142-110">ジェネレーション 2。</span><span class="sxs-lookup"><span data-stu-id="51142-110">Generation 2.</span></span>|  
|`CorDebug_LOH`|<span data-ttu-id="51142-111">大きなオブジェクトヒープ。</span><span class="sxs-lookup"><span data-stu-id="51142-111">The large object heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="51142-112">コメント</span><span class="sxs-lookup"><span data-stu-id="51142-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51142-113">要件</span><span class="sxs-lookup"><span data-stu-id="51142-113">Requirements</span></span>  
 <span data-ttu-id="51142-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51142-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51142-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="51142-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="51142-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="51142-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="51142-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51142-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51142-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="51142-118">See also</span></span>

- [<span data-ttu-id="51142-119">列挙型のデバッグ</span><span class="sxs-lookup"><span data-stu-id="51142-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
