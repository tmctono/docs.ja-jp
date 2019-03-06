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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fe8be6a7c18fff54825f981672f0f640bb60c35c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57482211"
---
# <a name="cordebuggctype-enumeration"></a><span data-ttu-id="2ee3b-102">CorDebugGCType 列挙型</span><span class="sxs-lookup"><span data-stu-id="2ee3b-102">CorDebugGCType Enumeration</span></span>
<span data-ttu-id="2ee3b-103">ガベージ コレクターがワークステーションまたはサーバーのどちらで実行されているかを示します。</span><span class="sxs-lookup"><span data-stu-id="2ee3b-103">Indicates whether the garbage collector is running on a workstation or a server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ee3b-104">構文</span><span class="sxs-lookup"><span data-stu-id="2ee3b-104">Syntax</span></span>  
  
```  
typedef enum CorDebugGCType {  
    CorDebugWorkstationGC  = 0,  
    CorDebugServerGC       = ( CorDebugWorkstationGC + 1 )  
} CorDebugGCType;  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ee3b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2ee3b-105">Parameters</span></span>  
  
## <a name="members"></a><span data-ttu-id="2ee3b-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="2ee3b-106">Members</span></span>  
  
|<span data-ttu-id="2ee3b-107">メンバー名</span><span class="sxs-lookup"><span data-stu-id="2ee3b-107">Member name</span></span>|<span data-ttu-id="2ee3b-108">説明</span><span class="sxs-lookup"><span data-stu-id="2ee3b-108">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebugWorkstationGC`|<span data-ttu-id="2ee3b-109">ガベージ コレクターは、ワークステーションで実行されています。</span><span class="sxs-lookup"><span data-stu-id="2ee3b-109">The garbage collector is running on a workstation.</span></span>|  
|`CorDebugServerGC`|<span data-ttu-id="2ee3b-110">ガベージ コレクターは、サーバーで実行します。</span><span class="sxs-lookup"><span data-stu-id="2ee3b-110">The garbage collector is running on a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ee3b-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="2ee3b-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ee3b-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="2ee3b-112">Requirements</span></span>  
 <span data-ttu-id="2ee3b-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ee3b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ee3b-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2ee3b-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2ee3b-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ee3b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ee3b-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ee3b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ee3b-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="2ee3b-117">See also</span></span>
- [<span data-ttu-id="2ee3b-118">列挙型のデバッグ</span><span class="sxs-lookup"><span data-stu-id="2ee3b-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
