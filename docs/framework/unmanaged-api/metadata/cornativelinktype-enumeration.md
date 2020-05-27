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
ms.openlocfilehash: 29f2401e2e3faccae05ca5249fcd7d9e89aacb46
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007612"
---
# <a name="cornativelinktype-enumeration"></a><span data-ttu-id="951f6-102">CorNativeLinkType 列挙型</span><span class="sxs-lookup"><span data-stu-id="951f6-102">CorNativeLinkType Enumeration</span></span>
<span data-ttu-id="951f6-103">ネイティブ コード内のリンクの種類を示す値を提供します。</span><span class="sxs-lookup"><span data-stu-id="951f6-103">Provides values that indicate the type linked in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="951f6-104">構文</span><span class="sxs-lookup"><span data-stu-id="951f6-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="951f6-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="951f6-105">Members</span></span>  
  
|<span data-ttu-id="951f6-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="951f6-106">Member</span></span>|<span data-ttu-id="951f6-107">説明</span><span class="sxs-lookup"><span data-stu-id="951f6-107">Description</span></span>|  
|------------|-----------------|  
|`nltNone`|<span data-ttu-id="951f6-108">キーワードが指定されていないことを示します。</span><span class="sxs-lookup"><span data-stu-id="951f6-108">Indicates that none of the keywords are specified.</span></span>|  
|`nltAnsi`|<span data-ttu-id="951f6-109">ANSI キーワードが指定されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="951f6-109">Indicates that an ANSI keyword is specified.</span></span>|  
|`nltUnicode`|<span data-ttu-id="951f6-110">Unicode キーワードが指定されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="951f6-110">Indicates that a Unicode keyword is specified</span></span>|  
|`nltAuto`|<span data-ttu-id="951f6-111">Auto キーワードが指定されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="951f6-111">Indicates that an auto keyword is specified.</span></span>|  
|`nltOle`|<span data-ttu-id="951f6-112">OLE キーワードが指定されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="951f6-112">Indicates that an OLE keyword is specified.</span></span>|  
|`nltMaxValue`|<span data-ttu-id="951f6-113">使用されていません。</span><span class="sxs-lookup"><span data-stu-id="951f6-113">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="951f6-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="951f6-114">Requirements</span></span>  
 <span data-ttu-id="951f6-115">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="951f6-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="951f6-116">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="951f6-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="951f6-117">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="951f6-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="951f6-118">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="951f6-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="951f6-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="951f6-119">See also</span></span>

- [<span data-ttu-id="951f6-120">メタデータ列挙体</span><span class="sxs-lookup"><span data-stu-id="951f6-120">Metadata Enumerations</span></span>](metadata-enumerations.md)
