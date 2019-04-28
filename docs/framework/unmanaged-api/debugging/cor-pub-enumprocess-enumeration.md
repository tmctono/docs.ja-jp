---
title: COR_PUB_ENUMPROCESS 列挙型
ms.date: 03/30/2017
api_name:
- COR_PUB_ENUMPROCESS
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_PUB_ENUMPROCESS
helpviewer_keywords:
- COR_PUB_ENUMPROCESS enumeration [.NET Framework debugging]
ms.assetid: 5d3ada6e-feea-47da-a7ed-b664107c137f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 02ff60852a85d003deb68cae96a184ac8d61c65f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61609400"
---
# <a name="corpubenumprocess-enumeration"></a><span data-ttu-id="3b7b3-102">COR_PUB_ENUMPROCESS 列挙型</span><span class="sxs-lookup"><span data-stu-id="3b7b3-102">COR_PUB_ENUMPROCESS Enumeration</span></span>
<span data-ttu-id="3b7b3-103">列挙するプロセスの型を識別します。</span><span class="sxs-lookup"><span data-stu-id="3b7b3-103">Identifies the type of process to be enumerated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b7b3-104">構文</span><span class="sxs-lookup"><span data-stu-id="3b7b3-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PUB_MANAGEDONLY    = 0x00000001  
} COR_PUB_ENUMPROCESS;  
```  
  
## <a name="members"></a><span data-ttu-id="3b7b3-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="3b7b3-105">Members</span></span>  
  
|<span data-ttu-id="3b7b3-106">メンバー名</span><span class="sxs-lookup"><span data-stu-id="3b7b3-106">Member name</span></span>|<span data-ttu-id="3b7b3-107">説明</span><span class="sxs-lookup"><span data-stu-id="3b7b3-107">Description</span></span>|  
|-----------------|-----------------|  
|`COR_PUB_MANAGEDONLY`|<span data-ttu-id="3b7b3-108">管理対象のプロセス。</span><span class="sxs-lookup"><span data-stu-id="3b7b3-108">A managed process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3b7b3-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="3b7b3-109">Remarks</span></span>  
 <span data-ttu-id="3b7b3-110">アンマネージ デバッグ API の現在のバージョンでは、マネージ プロセスのみを列挙します。</span><span class="sxs-lookup"><span data-stu-id="3b7b3-110">The current version of the unmanaged debugging API enumerates only managed processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b7b3-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="3b7b3-111">Requirements</span></span>  
 <span data-ttu-id="3b7b3-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b7b3-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b7b3-113">**ヘッダー:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="3b7b3-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="3b7b3-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3b7b3-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3b7b3-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b7b3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b7b3-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="3b7b3-116">See also</span></span>

- [<span data-ttu-id="3b7b3-117">列挙型のデバッグ</span><span class="sxs-lookup"><span data-stu-id="3b7b3-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
