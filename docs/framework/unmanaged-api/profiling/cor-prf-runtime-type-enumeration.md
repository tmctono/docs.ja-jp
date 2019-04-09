---
title: COR_PRF_RUNTIME_TYPE 列挙体
ms.date: 03/30/2017
api_name:
- COR_PRF_RUNTIME_TYPE Enumeration
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_RUNTIME_TYPE
helpviewer_keywords:
- COR_PRF_RUNTIME_TYPE enumeration [.NET Framework profiling]
ms.assetid: 35449514-333f-4918-9c60-7aa198d655d2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e57c622780f0bc92061fd2928ea861f904d9eb37
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59122110"
---
# <a name="corprfruntimetype-enumeration"></a><span data-ttu-id="50a98-102">COR_PRF_RUNTIME_TYPE 列挙体</span><span class="sxs-lookup"><span data-stu-id="50a98-102">COR_PRF_RUNTIME_TYPE Enumeration</span></span>
<span data-ttu-id="50a98-103">共通言語ランタイム (CLR) のバージョンを示す値を含みます。 デスクトップまたは CoreCLR は Silverlight で使用します。</span><span class="sxs-lookup"><span data-stu-id="50a98-103">Contains values that indicate the version of the common language runtime (CLR): desktop or CoreCLR, which is used in Silverlight.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50a98-104">構文</span><span class="sxs-lookup"><span data-stu-id="50a98-104">Syntax</span></span>  
  
```  
typedef enum  
{  
    COR_PRF_DESKTOP_CLR = 0x1,  
    COR_PRF_CORE_CLR    = 0x2,  
} COR_PRF_RUNTIME_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="50a98-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="50a98-105">Members</span></span>  
  
|<span data-ttu-id="50a98-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="50a98-106">Member</span></span>|<span data-ttu-id="50a98-107">説明</span><span class="sxs-lookup"><span data-stu-id="50a98-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_DESKTOP_CLR`|<span data-ttu-id="50a98-108">デスクトップ CLR のバージョン。</span><span class="sxs-lookup"><span data-stu-id="50a98-108">The desktop version of the CLR.</span></span>|  
|`COR_PRF_CORE_CLR`|<span data-ttu-id="50a98-109">Silverlight で使用される、CLR の core バージョン。</span><span class="sxs-lookup"><span data-stu-id="50a98-109">The core version of the CLR, used in Silverlight.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50a98-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="50a98-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50a98-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="50a98-111">Requirements</span></span>  
 <span data-ttu-id="50a98-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="50a98-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50a98-113">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="50a98-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="50a98-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="50a98-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="50a98-115">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="50a98-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="50a98-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="50a98-116">See also</span></span>

- [<span data-ttu-id="50a98-117">列挙体のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="50a98-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
