---
title: CorRefToDefCheck 列挙型
ms.date: 03/30/2017
api_name:
- CorRefToDefCheck
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRefToDefCheck
helpviewer_keywords:
- CorRefToDefCheck enumeration [.NET Framework metadata]
ms.assetid: f9a80f1a-55af-4459-b095-8441aae16119
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2ae87dd4538a9a8e88591f498c0ce77b51bfa852
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781617"
---
# <a name="correftodefcheck-enumeration"></a><span data-ttu-id="b2087-102">CorRefToDefCheck 列挙型</span><span class="sxs-lookup"><span data-stu-id="b2087-102">CorRefToDefCheck Enumeration</span></span>
<span data-ttu-id="b2087-103">コードを最適化するために定義に変換される、参照先アイテムを制御するフラグを指定します。</span><span class="sxs-lookup"><span data-stu-id="b2087-103">Specifies flags to control which referenced items are converted to their definitions in order to optimize the code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2087-104">構文</span><span class="sxs-lookup"><span data-stu-id="b2087-104">Syntax</span></span>  
  
```cpp  
typedef enum CorRefToDefCheck {  
    MDRefToDefDefault           = 0x00000003,  
    MDRefToDefAll               = 0xffffffff,  
    MDRefToDefNone              = 0x00000000,  
    MDTypeRefToDef              = 0x00000001,  
    MDMemberRefToDef            = 0x00000002  
} CorRefToDefCheck;  
```  
  
## <a name="members"></a><span data-ttu-id="b2087-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="b2087-105">Members</span></span>  
  
|<span data-ttu-id="b2087-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="b2087-106">Member</span></span>|<span data-ttu-id="b2087-107">説明</span><span class="sxs-lookup"><span data-stu-id="b2087-107">Description</span></span>|  
|------------|-----------------|  
|`MDRefToDefDefault`|<span data-ttu-id="b2087-108">定義に変換する必要があります型参照とメンバーの参照を指定します。</span><span class="sxs-lookup"><span data-stu-id="b2087-108">Specifies that type references and member references should be converted to definitions.</span></span> <span data-ttu-id="b2087-109">これは既定値 (`MDTypeRefToDef` &#124; `MDMemberRefToDef`)。</span><span class="sxs-lookup"><span data-stu-id="b2087-109">This is the default value (`MDTypeRefToDef` &#124; `MDMemberRefToDef`).</span></span>|  
|`MDRefToDefAll`|<span data-ttu-id="b2087-110">参照されるすべてのアイテムが定義に変換されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="b2087-110">Specifies that all referenced items should be converted to definitions.</span></span>|  
|`MDRefToDefNone`|<span data-ttu-id="b2087-111">定義に参照されている項目を変換しない必要がありますを指定します。</span><span class="sxs-lookup"><span data-stu-id="b2087-111">Specifies that no referenced items should be converted to definitions.</span></span>|  
|`MDTypeRefToDef`|<span data-ttu-id="b2087-112">型の参照のみが型定義に変換されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="b2087-112">Specifies that only type references should be converted to type definitions.</span></span>|  
|`MDMemberRefToDef`|<span data-ttu-id="b2087-113">メンバーの参照のみが定義に変換されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="b2087-113">Specifies that only member references should be converted to definitions.</span></span> <span data-ttu-id="b2087-114">つまり、メンバーの参照は、メソッドの定義またはフィールドの定義のいずれかに変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2087-114">That is, member references should be converted to either method definitions or field definitions.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b2087-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="b2087-115">Requirements</span></span>  
 <span data-ttu-id="b2087-116">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2087-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2087-117">**ヘッダー:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="b2087-117">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="b2087-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2087-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2087-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="b2087-119">See also</span></span>

- [<span data-ttu-id="b2087-120">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="b2087-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
