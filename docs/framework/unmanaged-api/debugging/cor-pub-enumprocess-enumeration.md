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
ms.openlocfilehash: 412e2bb7da7b5b3396342df169d56d2724ddb466
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740551"
---
# <a name="corpubenumprocess-enumeration"></a><span data-ttu-id="4b934-102">COR_PUB_ENUMPROCESS 列挙型</span><span class="sxs-lookup"><span data-stu-id="4b934-102">COR_PUB_ENUMPROCESS Enumeration</span></span>
<span data-ttu-id="4b934-103">列挙するプロセスの型を識別します。</span><span class="sxs-lookup"><span data-stu-id="4b934-103">Identifies the type of process to be enumerated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b934-104">構文</span><span class="sxs-lookup"><span data-stu-id="4b934-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PUB_MANAGEDONLY    = 0x00000001  
} COR_PUB_ENUMPROCESS;  
```  
  
## <a name="members"></a><span data-ttu-id="4b934-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="4b934-105">Members</span></span>  
  
|<span data-ttu-id="4b934-106">メンバー名</span><span class="sxs-lookup"><span data-stu-id="4b934-106">Member name</span></span>|<span data-ttu-id="4b934-107">説明</span><span class="sxs-lookup"><span data-stu-id="4b934-107">Description</span></span>|  
|-----------------|-----------------|  
|`COR_PUB_MANAGEDONLY`|<span data-ttu-id="4b934-108">管理対象のプロセス。</span><span class="sxs-lookup"><span data-stu-id="4b934-108">A managed process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4b934-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="4b934-109">Remarks</span></span>  
 <span data-ttu-id="4b934-110">アンマネージ デバッグ API の現在のバージョンでは、マネージ プロセスのみを列挙します。</span><span class="sxs-lookup"><span data-stu-id="4b934-110">The current version of the unmanaged debugging API enumerates only managed processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b934-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="4b934-111">Requirements</span></span>  
 <span data-ttu-id="4b934-112">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b934-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b934-113">**ヘッダー:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="4b934-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="4b934-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4b934-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4b934-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b934-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b934-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="4b934-116">See also</span></span>

- [<span data-ttu-id="4b934-117">列挙型のデバッグ</span><span class="sxs-lookup"><span data-stu-id="4b934-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
