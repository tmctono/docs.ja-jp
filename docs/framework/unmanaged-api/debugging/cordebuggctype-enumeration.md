---
title: CorDebugGCType 列挙体
ms.date: 03/30/2017
api_name:
- CorDebugGCType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugGCType
helpviewer_keywords:
- CorDebugGCType enumeration [.NET Framework debugging]
ms.assetid: 880ca92a-42d4-42a5-9b9c-c2848eb39c6a
topic_type:
- apiref
ms.openlocfilehash: 6f4c96517375df4cd249b72953bf37812a498c0c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789357"
---
# <a name="cordebuggctype-enumeration"></a><span data-ttu-id="db799-102">CorDebugGCType 列挙体</span><span class="sxs-lookup"><span data-stu-id="db799-102">CorDebugGCType Enumeration</span></span>
<span data-ttu-id="db799-103">ガベージ コレクターがワークステーションまたはサーバーのどちらで実行されているかを示します。</span><span class="sxs-lookup"><span data-stu-id="db799-103">Indicates whether the garbage collector is running on a workstation or a server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db799-104">構文</span><span class="sxs-lookup"><span data-stu-id="db799-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugGCType {  
    CorDebugWorkstationGC  = 0,  
    CorDebugServerGC       = ( CorDebugWorkstationGC + 1 )  
} CorDebugGCType;  
```  
  
## <a name="parameters"></a><span data-ttu-id="db799-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="db799-105">Parameters</span></span>  
  
## <a name="members"></a><span data-ttu-id="db799-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="db799-106">Members</span></span>  
  
|<span data-ttu-id="db799-107">メンバー名</span><span class="sxs-lookup"><span data-stu-id="db799-107">Member name</span></span>|<span data-ttu-id="db799-108">説明</span><span class="sxs-lookup"><span data-stu-id="db799-108">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebugWorkstationGC`|<span data-ttu-id="db799-109">ガベージコレクターはワークステーション上で実行されています。</span><span class="sxs-lookup"><span data-stu-id="db799-109">The garbage collector is running on a workstation.</span></span>|  
|`CorDebugServerGC`|<span data-ttu-id="db799-110">ガベージコレクターはサーバーで実行されています。</span><span class="sxs-lookup"><span data-stu-id="db799-110">The garbage collector is running on a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db799-111">コメント</span><span class="sxs-lookup"><span data-stu-id="db799-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db799-112">要件</span><span class="sxs-lookup"><span data-stu-id="db799-112">Requirements</span></span>  
 <span data-ttu-id="db799-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db799-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db799-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="db799-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="db799-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db799-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db799-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db799-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db799-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="db799-117">See also</span></span>

- [<span data-ttu-id="db799-118">列挙型のデバッグ</span><span class="sxs-lookup"><span data-stu-id="db799-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
