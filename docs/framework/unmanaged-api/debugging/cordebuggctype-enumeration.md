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
ms.openlocfilehash: f101fe2a84a26efb23f57bac3aaf4f0e64a4d36c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740031"
---
# <a name="cordebuggctype-enumeration"></a><span data-ttu-id="0adaa-102">CorDebugGCType 列挙型</span><span class="sxs-lookup"><span data-stu-id="0adaa-102">CorDebugGCType Enumeration</span></span>
<span data-ttu-id="0adaa-103">ガベージ コレクターがワークステーションまたはサーバーのどちらで実行されているかを示します。</span><span class="sxs-lookup"><span data-stu-id="0adaa-103">Indicates whether the garbage collector is running on a workstation or a server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0adaa-104">構文</span><span class="sxs-lookup"><span data-stu-id="0adaa-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugGCType {  
    CorDebugWorkstationGC  = 0,  
    CorDebugServerGC       = ( CorDebugWorkstationGC + 1 )  
} CorDebugGCType;  
```  
  
## <a name="parameters"></a><span data-ttu-id="0adaa-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0adaa-105">Parameters</span></span>  
  
## <a name="members"></a><span data-ttu-id="0adaa-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="0adaa-106">Members</span></span>  
  
|<span data-ttu-id="0adaa-107">メンバー名</span><span class="sxs-lookup"><span data-stu-id="0adaa-107">Member name</span></span>|<span data-ttu-id="0adaa-108">説明</span><span class="sxs-lookup"><span data-stu-id="0adaa-108">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebugWorkstationGC`|<span data-ttu-id="0adaa-109">ガベージ コレクターは、ワークステーションで実行されています。</span><span class="sxs-lookup"><span data-stu-id="0adaa-109">The garbage collector is running on a workstation.</span></span>|  
|`CorDebugServerGC`|<span data-ttu-id="0adaa-110">ガベージ コレクターは、サーバーで実行します。</span><span class="sxs-lookup"><span data-stu-id="0adaa-110">The garbage collector is running on a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0adaa-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="0adaa-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0adaa-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="0adaa-112">Requirements</span></span>  
 <span data-ttu-id="0adaa-113">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0adaa-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0adaa-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0adaa-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0adaa-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0adaa-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0adaa-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0adaa-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0adaa-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="0adaa-117">See also</span></span>

- [<span data-ttu-id="0adaa-118">列挙型のデバッグ</span><span class="sxs-lookup"><span data-stu-id="0adaa-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
