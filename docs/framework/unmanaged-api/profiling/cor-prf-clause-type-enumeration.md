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
ms.openlocfilehash: 18197f0c500a205a66bdda8a9401f31d4208ae67
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780433"
---
# <a name="corprfclausetype-enumeration"></a><span data-ttu-id="d36cd-102">COR_PRF_CLAUSE_TYPE 列挙型</span><span class="sxs-lookup"><span data-stu-id="d36cd-102">COR_PRF_CLAUSE_TYPE Enumeration</span></span>
<span data-ttu-id="d36cd-103">コードが入った、または出た例外句のタイプを示します。</span><span class="sxs-lookup"><span data-stu-id="d36cd-103">Indicates the type of exception clause that the code has just entered or left.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d36cd-104">構文</span><span class="sxs-lookup"><span data-stu-id="d36cd-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_CLAUSE_NONE = 0,  
    COR_PRF_CLAUSE_FILTER = 1,  
    COR_PRF_CLAUSE_CATCH = 2,  
    COR_PRF_CLAUSE_FINALLY = 3,  
} COR_PRF_CLAUSE_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="d36cd-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="d36cd-105">Members</span></span>  
  
|<span data-ttu-id="d36cd-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="d36cd-106">Member</span></span>|<span data-ttu-id="d36cd-107">説明</span><span class="sxs-lookup"><span data-stu-id="d36cd-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_CLAUSE_NONE`|<span data-ttu-id="d36cd-108">例外の句が無効です。</span><span class="sxs-lookup"><span data-stu-id="d36cd-108">The exception clause is not valid.</span></span>|  
|`COR_PRF_CLAUSE_FILTER`|<span data-ttu-id="d36cd-109">例外の句は、フィルター式です。</span><span class="sxs-lookup"><span data-stu-id="d36cd-109">The exception clause is a filter expression.</span></span>|  
|`COR_PRF_CLAUSE_CATCH`|<span data-ttu-id="d36cd-110">例外の句は、`catch`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="d36cd-110">The exception clause is a `catch` statement.</span></span>|  
|`COR_PRF_CLAUSE_FINALLY`|<span data-ttu-id="d36cd-111">例外の句は、`finally`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="d36cd-111">The exception clause is a `finally` statement.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d36cd-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="d36cd-112">Requirements</span></span>  
 <span data-ttu-id="d36cd-113">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d36cd-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d36cd-114">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d36cd-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d36cd-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d36cd-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d36cd-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d36cd-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d36cd-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="d36cd-117">See also</span></span>

- [<span data-ttu-id="d36cd-118">列挙型のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="d36cd-118">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
