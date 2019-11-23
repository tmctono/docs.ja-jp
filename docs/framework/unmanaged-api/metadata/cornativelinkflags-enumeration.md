---
title: CorNativeLinkFlags 列挙型
ms.date: 03/30/2017
api_name:
- CorNativeLinkFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNativeLinkFlags
helpviewer_keywords:
- CorNativeLinkFlags enumeration [.NET Framework metadata]
ms.assetid: 8027df7c-cfad-4724-bda0-7538d9519070
topic_type:
- apiref
ms.openlocfilehash: 1362efbf518310240ce665badc93810d1c0b9b89
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450190"
---
# <a name="cornativelinkflags-enumeration"></a><span data-ttu-id="d0813-102">CorNativeLinkFlags 列挙型</span><span class="sxs-lookup"><span data-stu-id="d0813-102">CorNativeLinkFlags Enumeration</span></span>
<span data-ttu-id="d0813-103">ネイティブ コードをリンクするときに、リンカーが使用するフラグ値を提供します。</span><span class="sxs-lookup"><span data-stu-id="d0813-103">Provides flag values used by the linker when linking native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0813-104">構文</span><span class="sxs-lookup"><span data-stu-id="d0813-104">Syntax</span></span>  
  
```cpp  
typedef enum  
{  
    nlfNone         = 0x00,  
    nlfLastError    = 0x01,  
    nlfNoMangle     = 0x02,  
    nlfMaxValue     = 0x03  
} CorNativeLinkFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="d0813-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="d0813-105">Members</span></span>  
  
|<span data-ttu-id="d0813-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="d0813-106">Member</span></span>|<span data-ttu-id="d0813-107">説明</span><span class="sxs-lookup"><span data-stu-id="d0813-107">Description</span></span>|  
|------------|-----------------|  
|`nlfNone`|<span data-ttu-id="d0813-108">Indicates no flags.</span><span class="sxs-lookup"><span data-stu-id="d0813-108">Indicates no flags.</span></span>|  
|`nlfLastError`|<span data-ttu-id="d0813-109">Indicates a `setLastError` keyword.</span><span class="sxs-lookup"><span data-stu-id="d0813-109">Indicates a `setLastError` keyword.</span></span>|  
|`nlfNoMangle`|<span data-ttu-id="d0813-110">Indicates a `nomangle` keyword.</span><span class="sxs-lookup"><span data-stu-id="d0813-110">Indicates a `nomangle` keyword.</span></span>|  
|`nlfMaxValue`|<span data-ttu-id="d0813-111">使用しません。</span><span class="sxs-lookup"><span data-stu-id="d0813-111">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d0813-112">［要件］</span><span class="sxs-lookup"><span data-stu-id="d0813-112">Requirements</span></span>  
 <span data-ttu-id="d0813-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0813-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0813-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d0813-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d0813-115">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d0813-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d0813-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0813-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0813-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="d0813-117">See also</span></span>

- [<span data-ttu-id="d0813-118">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="d0813-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
