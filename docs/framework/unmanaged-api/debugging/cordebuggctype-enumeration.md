---
title: CorDebugGCType 列挙型
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
ms.openlocfilehash: b954aa0e4db10fd4b3bde951c7f27d18b8634f5a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132181"
---
# <a name="cordebuggctype-enumeration"></a><span data-ttu-id="4bd64-102">CorDebugGCType 列挙型</span><span class="sxs-lookup"><span data-stu-id="4bd64-102">CorDebugGCType Enumeration</span></span>
<span data-ttu-id="4bd64-103">ガベージ コレクターがワークステーションまたはサーバーのどちらで実行されているかを示します。</span><span class="sxs-lookup"><span data-stu-id="4bd64-103">Indicates whether the garbage collector is running on a workstation or a server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bd64-104">構文</span><span class="sxs-lookup"><span data-stu-id="4bd64-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugGCType {  
    CorDebugWorkstationGC  = 0,  
    CorDebugServerGC       = ( CorDebugWorkstationGC + 1 )  
} CorDebugGCType;  
```  
  
## <a name="parameters"></a><span data-ttu-id="4bd64-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4bd64-105">Parameters</span></span>  
  
## <a name="members"></a><span data-ttu-id="4bd64-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="4bd64-106">Members</span></span>  
  
|<span data-ttu-id="4bd64-107">メンバー名</span><span class="sxs-lookup"><span data-stu-id="4bd64-107">Member name</span></span>|<span data-ttu-id="4bd64-108">説明</span><span class="sxs-lookup"><span data-stu-id="4bd64-108">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebugWorkstationGC`|<span data-ttu-id="4bd64-109">ガベージコレクターはワークステーション上で実行されています。</span><span class="sxs-lookup"><span data-stu-id="4bd64-109">The garbage collector is running on a workstation.</span></span>|  
|`CorDebugServerGC`|<span data-ttu-id="4bd64-110">ガベージコレクターはサーバーで実行されています。</span><span class="sxs-lookup"><span data-stu-id="4bd64-110">The garbage collector is running on a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4bd64-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="4bd64-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4bd64-112">［要件］</span><span class="sxs-lookup"><span data-stu-id="4bd64-112">Requirements</span></span>  
 <span data-ttu-id="4bd64-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4bd64-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4bd64-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4bd64-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4bd64-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4bd64-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4bd64-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4bd64-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bd64-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="4bd64-117">See also</span></span>

- [<span data-ttu-id="4bd64-118">列挙型のデバッグ</span><span class="sxs-lookup"><span data-stu-id="4bd64-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
