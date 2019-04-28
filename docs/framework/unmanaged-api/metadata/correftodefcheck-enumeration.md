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
ms.openlocfilehash: 82abeb0ce3db075d794787bb1fcd5bc18321bef2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61906179"
---
# <a name="correftodefcheck-enumeration"></a><span data-ttu-id="9f71b-102">CorRefToDefCheck 列挙型</span><span class="sxs-lookup"><span data-stu-id="9f71b-102">CorRefToDefCheck Enumeration</span></span>
<span data-ttu-id="9f71b-103">コードを最適化するために定義に変換される、参照先アイテムを制御するフラグを指定します。</span><span class="sxs-lookup"><span data-stu-id="9f71b-103">Specifies flags to control which referenced items are converted to their definitions in order to optimize the code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f71b-104">構文</span><span class="sxs-lookup"><span data-stu-id="9f71b-104">Syntax</span></span>  
  
```  
typedef enum CorRefToDefCheck {  
    MDRefToDefDefault           = 0x00000003,  
    MDRefToDefAll               = 0xffffffff,  
    MDRefToDefNone              = 0x00000000,  
    MDTypeRefToDef              = 0x00000001,  
    MDMemberRefToDef            = 0x00000002  
} CorRefToDefCheck;  
```  
  
## <a name="members"></a><span data-ttu-id="9f71b-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="9f71b-105">Members</span></span>  
  
|<span data-ttu-id="9f71b-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="9f71b-106">Member</span></span>|<span data-ttu-id="9f71b-107">説明</span><span class="sxs-lookup"><span data-stu-id="9f71b-107">Description</span></span>|  
|------------|-----------------|  
|`MDRefToDefDefault`|<span data-ttu-id="9f71b-108">定義に変換する必要があります型参照とメンバーの参照を指定します。</span><span class="sxs-lookup"><span data-stu-id="9f71b-108">Specifies that type references and member references should be converted to definitions.</span></span> <span data-ttu-id="9f71b-109">これは既定値 (`MDTypeRefToDef` &#124; `MDMemberRefToDef`)。</span><span class="sxs-lookup"><span data-stu-id="9f71b-109">This is the default value (`MDTypeRefToDef` &#124; `MDMemberRefToDef`).</span></span>|  
|`MDRefToDefAll`|<span data-ttu-id="9f71b-110">参照されるすべてのアイテムが定義に変換されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="9f71b-110">Specifies that all referenced items should be converted to definitions.</span></span>|  
|`MDRefToDefNone`|<span data-ttu-id="9f71b-111">定義に参照されている項目を変換しない必要がありますを指定します。</span><span class="sxs-lookup"><span data-stu-id="9f71b-111">Specifies that no referenced items should be converted to definitions.</span></span>|  
|`MDTypeRefToDef`|<span data-ttu-id="9f71b-112">型の参照のみが型定義に変換されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="9f71b-112">Specifies that only type references should be converted to type definitions.</span></span>|  
|`MDMemberRefToDef`|<span data-ttu-id="9f71b-113">メンバーの参照のみが定義に変換されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="9f71b-113">Specifies that only member references should be converted to definitions.</span></span> <span data-ttu-id="9f71b-114">つまり、メンバーの参照は、メソッドの定義またはフィールドの定義のいずれかに変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f71b-114">That is, member references should be converted to either method definitions or field definitions.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9f71b-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="9f71b-115">Requirements</span></span>  
 <span data-ttu-id="9f71b-116">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f71b-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f71b-117">**ヘッダー:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="9f71b-117">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="9f71b-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f71b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f71b-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="9f71b-119">See also</span></span>

- [<span data-ttu-id="9f71b-120">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="9f71b-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
