---
title: CorNativeLinkType 列挙型
ms.date: 03/30/2017
api_name:
- CorNativeLinkType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNativeLinkType
helpviewer_keywords:
- CorNativeLinkType enumeration [.NET Framework metadata]
ms.assetid: 4f86ff37-2dab-4e64-819a-76b3bfe828ff
topic_type:
- apiref
ms.openlocfilehash: 718e41e16c07265d8a36b8f6124d99cd3490f7be
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436616"
---
# <a name="cornativelinktype-enumeration"></a><span data-ttu-id="090cc-102">CorNativeLinkType 列挙型</span><span class="sxs-lookup"><span data-stu-id="090cc-102">CorNativeLinkType Enumeration</span></span>
<span data-ttu-id="090cc-103">ネイティブ コード内のリンクの種類を示す値を提供します。</span><span class="sxs-lookup"><span data-stu-id="090cc-103">Provides values that indicate the type linked in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="090cc-104">構文</span><span class="sxs-lookup"><span data-stu-id="090cc-104">Syntax</span></span>  
  
```cpp  
typedef enum   
{  
    nltNone       = 1,  
    nltAnsi       = 2,  
    nltUnicode    = 3,  
    nltAuto       = 4,  
    nltOle        = 5,  
    nltMaxValue   = 7  
} CorNativeLinkType;  
```  
  
## <a name="members"></a><span data-ttu-id="090cc-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="090cc-105">Members</span></span>  
  
|<span data-ttu-id="090cc-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="090cc-106">Member</span></span>|<span data-ttu-id="090cc-107">説明</span><span class="sxs-lookup"><span data-stu-id="090cc-107">Description</span></span>|  
|------------|-----------------|  
|`nltNone`|<span data-ttu-id="090cc-108">Indicates that none of the keywords are specified.</span><span class="sxs-lookup"><span data-stu-id="090cc-108">Indicates that none of the keywords are specified.</span></span>|  
|`nltAnsi`|<span data-ttu-id="090cc-109">Indicates that an ANSI keyword is specified.</span><span class="sxs-lookup"><span data-stu-id="090cc-109">Indicates that an ANSI keyword is specified.</span></span>|  
|`nltUnicode`|<span data-ttu-id="090cc-110">Indicates that a Unicode keyword is specified</span><span class="sxs-lookup"><span data-stu-id="090cc-110">Indicates that a Unicode keyword is specified</span></span>|  
|`nltAuto`|<span data-ttu-id="090cc-111">Indicates that an auto keyword is specified.</span><span class="sxs-lookup"><span data-stu-id="090cc-111">Indicates that an auto keyword is specified.</span></span>|  
|`nltOle`|<span data-ttu-id="090cc-112">Indicates that an OLE keyword is specified.</span><span class="sxs-lookup"><span data-stu-id="090cc-112">Indicates that an OLE keyword is specified.</span></span>|  
|`nltMaxValue`|<span data-ttu-id="090cc-113">使用しません。</span><span class="sxs-lookup"><span data-stu-id="090cc-113">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="090cc-114">［要件］</span><span class="sxs-lookup"><span data-stu-id="090cc-114">Requirements</span></span>  
 <span data-ttu-id="090cc-115">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="090cc-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="090cc-116">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="090cc-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="090cc-117">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="090cc-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="090cc-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="090cc-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="090cc-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="090cc-119">See also</span></span>

- [<span data-ttu-id="090cc-120">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="090cc-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
