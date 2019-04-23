---
title: CLR_DEBUGGING_VERSION 構造体
ms.date: 03/30/2017
api_name:
- CLR_DEBUGGING_VERSION
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CLR_DEBUGGING_VERSION
helpviewer_keywords:
- CLR_DEBUGGING_VERSION structure [.NET Framework debugging]
ms.assetid: 4d821186-3ddf-405a-ac44-d79438a9f7f3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 87f938a7119abe4a88da65bd779a5f4a02499516
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59117119"
---
# <a name="clrdebuggingversion-structure"></a><span data-ttu-id="05cc7-102">CLR_DEBUGGING_VERSION 構造体</span><span class="sxs-lookup"><span data-stu-id="05cc7-102">CLR_DEBUGGING_VERSION Structure</span></span>
<span data-ttu-id="05cc7-103">デバッグのために共通言語ランタイム (CLR) の製品バージョンを定義します。</span><span class="sxs-lookup"><span data-stu-id="05cc7-103">Defines the product version of the common language runtime (CLR) for debugging purposes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05cc7-104">構文</span><span class="sxs-lookup"><span data-stu-id="05cc7-104">Syntax</span></span>  
  
```  
typedef struct _CLR_DEBUGGING_VERSION  
{  
    WORD wStructVersion;
    WORD wMajor;
    WORD wMinor;
    WORD wBuild;
    WORD wRevision;
} CLR_DEBUGGING_VERSION;
```  
  
## <a name="members"></a><span data-ttu-id="05cc7-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="05cc7-105">Members</span></span>  
  
|<span data-ttu-id="05cc7-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="05cc7-106">Member</span></span>|<span data-ttu-id="05cc7-107">説明</span><span class="sxs-lookup"><span data-stu-id="05cc7-107">Description</span></span>|  
|------------|-----------------|  
|`wStructVersion`|<span data-ttu-id="05cc7-108">構造のバージョン番号</span><span class="sxs-lookup"><span data-stu-id="05cc7-108">The structure version number</span></span>|  
|`wMajor`|<span data-ttu-id="05cc7-109">メジャー バージョン番号。</span><span class="sxs-lookup"><span data-stu-id="05cc7-109">The major version number.</span></span>|  
|`wMinor`|<span data-ttu-id="05cc7-110">マイナー バージョン番号。</span><span class="sxs-lookup"><span data-stu-id="05cc7-110">The minor version number.</span></span>|  
|`wBuild`|<span data-ttu-id="05cc7-111">ビルド番号。</span><span class="sxs-lookup"><span data-stu-id="05cc7-111">The build number.</span></span>|  
|`wRevision`|<span data-ttu-id="05cc7-112">リビジョン番号。</span><span class="sxs-lookup"><span data-stu-id="05cc7-112">The revision number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="05cc7-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="05cc7-113">Remarks</span></span>  
 <span data-ttu-id="05cc7-114">`CLR_DEBUGGING_VERSION`構造がただし COR_VERSION 構造体と同じでは、`CLR_DEBUGGING_VERSION`構造は追加の構造のバージョン フィールドを提供します (`wStructVersion`)。</span><span class="sxs-lookup"><span data-stu-id="05cc7-114">The `CLR_DEBUGGING_VERSION` structure is the same as the COR_VERSION structure, however, the `CLR_DEBUGGING_VERSION` structure provides an additional structure version field (`wStructVersion`).</span></span> <span data-ttu-id="05cc7-115">現時点では、このフィールドは 0 に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="05cc7-115">Currently, this field must be set to zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05cc7-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="05cc7-116">Requirements</span></span>  
 <span data-ttu-id="05cc7-117">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="05cc7-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05cc7-118">**ヘッダー:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="05cc7-118">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="05cc7-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="05cc7-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="05cc7-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05cc7-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05cc7-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="05cc7-121">See also</span></span>

- [<span data-ttu-id="05cc7-122">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="05cc7-122">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="05cc7-123">デバッグ</span><span class="sxs-lookup"><span data-stu-id="05cc7-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
