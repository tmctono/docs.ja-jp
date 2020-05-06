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
ms.openlocfilehash: 8dd070d2c895a94ac996be81e672bd67f59b83b7
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795899"
---
# <a name="cordebuggctype-enumeration"></a><span data-ttu-id="6387b-102">CorDebugGCType 列挙型</span><span class="sxs-lookup"><span data-stu-id="6387b-102">CorDebugGCType Enumeration</span></span>
<span data-ttu-id="6387b-103">ガベージ コレクターがワークステーションまたはサーバーのどちらで実行されているかを示します。</span><span class="sxs-lookup"><span data-stu-id="6387b-103">Indicates whether the garbage collector is running on a workstation or a server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6387b-104">構文</span><span class="sxs-lookup"><span data-stu-id="6387b-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugGCType {  
    CorDebugWorkstationGC  = 0,  
    CorDebugServerGC       = ( CorDebugWorkstationGC + 1 )  
} CorDebugGCType;  
```  
  
## <a name="parameters"></a><span data-ttu-id="6387b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6387b-105">Parameters</span></span>  
  
## <a name="members"></a><span data-ttu-id="6387b-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="6387b-106">Members</span></span>  
  
|<span data-ttu-id="6387b-107">メンバー名</span><span class="sxs-lookup"><span data-stu-id="6387b-107">Member name</span></span>|<span data-ttu-id="6387b-108">説明</span><span class="sxs-lookup"><span data-stu-id="6387b-108">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebugWorkstationGC`|<span data-ttu-id="6387b-109">ガベージコレクターはワークステーション上で実行されています。</span><span class="sxs-lookup"><span data-stu-id="6387b-109">The garbage collector is running on a workstation.</span></span>|  
|`CorDebugServerGC`|<span data-ttu-id="6387b-110">ガベージコレクターはサーバーで実行されています。</span><span class="sxs-lookup"><span data-stu-id="6387b-110">The garbage collector is running on a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6387b-111">解説</span><span class="sxs-lookup"><span data-stu-id="6387b-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6387b-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="6387b-112">Requirements</span></span>  
 <span data-ttu-id="6387b-113">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6387b-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6387b-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6387b-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6387b-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6387b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6387b-116">**.NET Framework のバージョン:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6387b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6387b-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="6387b-117">See also</span></span>

- [<span data-ttu-id="6387b-118">列挙体のデバッグ</span><span class="sxs-lookup"><span data-stu-id="6387b-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
