---
title: COR_PRF_CLAUSE_TYPE 列挙型
ms.date: 03/30/2017
api_name:
- COR_PRF_CLAUSE_TYPE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_CLAUSE_TYPE
helpviewer_keywords:
- COR_PRF_CLAUSE_TYPE enumeration [.NET Framework profiling]
ms.assetid: f64c325a-ed3a-4aaf-b847-a88edbc4fefc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 861f4c18f4c5151dc7215d300775928b88f018aa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59090629"
---
# <a name="corprfclausetype-enumeration"></a><span data-ttu-id="8b246-102">COR_PRF_CLAUSE_TYPE 列挙型</span><span class="sxs-lookup"><span data-stu-id="8b246-102">COR_PRF_CLAUSE_TYPE Enumeration</span></span>
<span data-ttu-id="8b246-103">コードが入った、または出た例外句のタイプを示します。</span><span class="sxs-lookup"><span data-stu-id="8b246-103">Indicates the type of exception clause that the code has just entered or left.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b246-104">構文</span><span class="sxs-lookup"><span data-stu-id="8b246-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_CLAUSE_NONE = 0,  
    COR_PRF_CLAUSE_FILTER = 1,  
    COR_PRF_CLAUSE_CATCH = 2,  
    COR_PRF_CLAUSE_FINALLY = 3,  
} COR_PRF_CLAUSE_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="8b246-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="8b246-105">Members</span></span>  
  
|<span data-ttu-id="8b246-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="8b246-106">Member</span></span>|<span data-ttu-id="8b246-107">説明</span><span class="sxs-lookup"><span data-stu-id="8b246-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_CLAUSE_NONE`|<span data-ttu-id="8b246-108">例外の句が無効です。</span><span class="sxs-lookup"><span data-stu-id="8b246-108">The exception clause is not valid.</span></span>|  
|`COR_PRF_CLAUSE_FILTER`|<span data-ttu-id="8b246-109">例外の句は、フィルター式です。</span><span class="sxs-lookup"><span data-stu-id="8b246-109">The exception clause is a filter expression.</span></span>|  
|`COR_PRF_CLAUSE_CATCH`|<span data-ttu-id="8b246-110">例外の句は、`catch`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="8b246-110">The exception clause is a `catch` statement.</span></span>|  
|`COR_PRF_CLAUSE_FINALLY`|<span data-ttu-id="8b246-111">例外の句は、`finally`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="8b246-111">The exception clause is a `finally` statement.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8b246-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="8b246-112">Requirements</span></span>  
 <span data-ttu-id="8b246-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b246-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b246-114">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8b246-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8b246-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8b246-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="8b246-116">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="8b246-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8b246-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="8b246-117">See also</span></span>

- [<span data-ttu-id="8b246-118">列挙体のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="8b246-118">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
