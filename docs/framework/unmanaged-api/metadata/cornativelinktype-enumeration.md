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
ms.openlocfilehash: 0b613ebacdff82a29fdbc3f4caa0f2b8bb5d3f6a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176163"
---
# <a name="cornativelinktype-enumeration"></a><span data-ttu-id="3a3f0-102">CorNativeLinkType 列挙型</span><span class="sxs-lookup"><span data-stu-id="3a3f0-102">CorNativeLinkType Enumeration</span></span>
<span data-ttu-id="3a3f0-103">ネイティブ コード内のリンクの種類を示す値を提供します。</span><span class="sxs-lookup"><span data-stu-id="3a3f0-103">Provides values that indicate the type linked in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a3f0-104">構文</span><span class="sxs-lookup"><span data-stu-id="3a3f0-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="3a3f0-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="3a3f0-105">Members</span></span>  
  
|<span data-ttu-id="3a3f0-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="3a3f0-106">Member</span></span>|<span data-ttu-id="3a3f0-107">説明</span><span class="sxs-lookup"><span data-stu-id="3a3f0-107">Description</span></span>|  
|------------|-----------------|  
|`nltNone`|<span data-ttu-id="3a3f0-108">キーワードが指定されていない場合に指定します。</span><span class="sxs-lookup"><span data-stu-id="3a3f0-108">Indicates that none of the keywords are specified.</span></span>|  
|`nltAnsi`|<span data-ttu-id="3a3f0-109">ANSI キーワードが指定されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="3a3f0-109">Indicates that an ANSI keyword is specified.</span></span>|  
|`nltUnicode`|<span data-ttu-id="3a3f0-110">Unicode キーワードが指定されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="3a3f0-110">Indicates that a Unicode keyword is specified</span></span>|  
|`nltAuto`|<span data-ttu-id="3a3f0-111">auto キーワードが指定されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="3a3f0-111">Indicates that an auto keyword is specified.</span></span>|  
|`nltOle`|<span data-ttu-id="3a3f0-112">OLE キーワードが指定されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="3a3f0-112">Indicates that an OLE keyword is specified.</span></span>|  
|`nltMaxValue`|<span data-ttu-id="3a3f0-113">使用されていません。</span><span class="sxs-lookup"><span data-stu-id="3a3f0-113">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3a3f0-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="3a3f0-114">Requirements</span></span>  
 <span data-ttu-id="3a3f0-115">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a3f0-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a3f0-116">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="3a3f0-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3a3f0-117">**ライブラリ:** MsCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="3a3f0-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3a3f0-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a3f0-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a3f0-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="3a3f0-119">See also</span></span>

- [<span data-ttu-id="3a3f0-120">メタデータ列挙体</span><span class="sxs-lookup"><span data-stu-id="3a3f0-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
