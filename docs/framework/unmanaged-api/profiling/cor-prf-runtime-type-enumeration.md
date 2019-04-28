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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61599183"
---
# <a name="corprfruntimetype-enumeration"></a><span data-ttu-id="f6a89-102">COR_PRF_RUNTIME_TYPE 列挙体</span><span class="sxs-lookup"><span data-stu-id="f6a89-102">COR_PRF_RUNTIME_TYPE Enumeration</span></span>
<span data-ttu-id="f6a89-103">共通言語ランタイム (CLR) のバージョンを示す値を含みます。 デスクトップまたは CoreCLR は Silverlight で使用します。</span><span class="sxs-lookup"><span data-stu-id="f6a89-103">Contains values that indicate the version of the common language runtime (CLR): desktop or CoreCLR, which is used in Silverlight.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6a89-104">構文</span><span class="sxs-lookup"><span data-stu-id="f6a89-104">Syntax</span></span>  
  
```  
typedef enum  
{  
    COR_PRF_DESKTOP_CLR = 0x1,  
    COR_PRF_CORE_CLR    = 0x2,  
} COR_PRF_RUNTIME_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="f6a89-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="f6a89-105">Members</span></span>  
  
|<span data-ttu-id="f6a89-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="f6a89-106">Member</span></span>|<span data-ttu-id="f6a89-107">説明</span><span class="sxs-lookup"><span data-stu-id="f6a89-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_DESKTOP_CLR`|<span data-ttu-id="f6a89-108">デスクトップ CLR のバージョン。</span><span class="sxs-lookup"><span data-stu-id="f6a89-108">The desktop version of the CLR.</span></span>|  
|`COR_PRF_CORE_CLR`|<span data-ttu-id="f6a89-109">Silverlight で使用される、CLR の core バージョン。</span><span class="sxs-lookup"><span data-stu-id="f6a89-109">The core version of the CLR, used in Silverlight.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f6a89-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="f6a89-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6a89-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="f6a89-111">Requirements</span></span>  
 <span data-ttu-id="f6a89-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6a89-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6a89-113">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f6a89-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f6a89-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f6a89-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f6a89-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6a89-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6a89-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="f6a89-116">See also</span></span>

- [<span data-ttu-id="f6a89-117">列挙型のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="f6a89-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
