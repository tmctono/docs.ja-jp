---
title: IDENTITY_ATTRIBUTE 構造体
ms.date: 03/30/2017
api_name:
- IDENTITY_ATTRIBUTE
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDENTITY_ATTRIBUTE
helpviewer_keywords:
- IDENTITY_ATTRIBUTE structure [.NET Framework fusion]
ms.assetid: 1ee7c434-9681-4fa8-badd-652cb1a9742b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e0bcabb32d50b236d42a555c073b50ba3a234dde
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796489"
---
# <a name="identity_attribute-structure"></a><span data-ttu-id="f3728-102">IDENTITY_ATTRIBUTE 構造体</span><span class="sxs-lookup"><span data-stu-id="f3728-102">IDENTITY_ATTRIBUTE Structure</span></span>
<span data-ttu-id="f3728-103">[IDefinitionIdentity](idefinitionidentity-interface.md)インスタンスに関するメタデータ属性情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="f3728-103">Contains metadata attribute information about an [IDefinitionIdentity](idefinitionidentity-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3728-104">構文</span><span class="sxs-lookup"><span data-stu-id="f3728-104">Syntax</span></span>  
  
```cpp  
typedef struct _IDENTITY_ATTRIBUTE {  
    LPCWSTR  pszNamespace;  
    LPCWSTR  pszName;  
    LPCWSTR  pszValue;  
} IDENTITY_ATTRIBUTE;  
```  
  
## <a name="members"></a><span data-ttu-id="f3728-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="f3728-105">Members</span></span>  
  
|<span data-ttu-id="f3728-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="f3728-106">Member</span></span>|<span data-ttu-id="f3728-107">説明</span><span class="sxs-lookup"><span data-stu-id="f3728-107">Description</span></span>|  
|------------|-----------------|  
|`pszNamespace`|<span data-ttu-id="f3728-108">属性が含まれている名前空間を含む null で終わる文字列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="f3728-108">A pointer to a null-terminated character string that contains the namespace the attribute is in.</span></span>|  
|`pszName`|<span data-ttu-id="f3728-109">属性の名前を含む null で終わる文字列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="f3728-109">A pointer to a null-terminated character string that contains the name of the attribute.</span></span>|  
|`pszValue`|<span data-ttu-id="f3728-110">属性の値を格納している null で終わる文字列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="f3728-110">A pointer to a null-terminated character string that contains the value of the attribute.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f3728-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="f3728-111">Remarks</span></span>  
 <span data-ttu-id="f3728-112">構造`IDENTITY_ATTRIBUTE`体には、null で終わる文字列への3つのポインターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f3728-112">The `IDENTITY_ATTRIBUTE` structure contains three pointers to null-terminated character strings.</span></span> <span data-ttu-id="f3728-113">これら3つの文字列は、1つの属性を表します。</span><span class="sxs-lookup"><span data-stu-id="f3728-113">These three strings describe one attribute.</span></span>  
  
 <span data-ttu-id="f3728-114">`IDENTITY_ATTRIBUTE`構造体のインスタンスは、 [IDENTITY_ATTRIBUTE_BLOB](identity-attribute-blob-structure.md)構造体のインスタンスに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="f3728-114">An instance of an `IDENTITY_ATTRIBUTE` structure is associated with an instance of an [IDENTITY_ATTRIBUTE_BLOB](identity-attribute-blob-structure.md) structure.</span></span> <span data-ttu-id="f3728-115">構造体には実際の文字列が含まれ`IDENTITY_ATTRIBUTE_BLOB` 、対応する構造体には、 `IDENTITY_ATTRIBUTE`構造体に示されている3つの文字列へのオフセットが一覧表示されます。 `IDENTITY_ATTRIBUTE`</span><span class="sxs-lookup"><span data-stu-id="f3728-115">The `IDENTITY_ATTRIBUTE` structure contains the actual strings, and the corresponding `IDENTITY_ATTRIBUTE_BLOB` structure lists the offsets to the three strings listed in the `IDENTITY_ATTRIBUTE` structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3728-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="f3728-116">Requirements</span></span>  
 <span data-ttu-id="f3728-117">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3728-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3728-118">**ヘッダー:** 分離 .h</span><span class="sxs-lookup"><span data-stu-id="f3728-118">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="f3728-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3728-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3728-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="f3728-120">See also</span></span>

- [<span data-ttu-id="f3728-121">IDefinitionIdentity インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f3728-121">IDefinitionIdentity Interface</span></span>](idefinitionidentity-interface.md)
- [<span data-ttu-id="f3728-122">IDENTITY_ATTRIBUTE_BLOB 構造体</span><span class="sxs-lookup"><span data-stu-id="f3728-122">IDENTITY_ATTRIBUTE_BLOB Structure</span></span>](identity-attribute-blob-structure.md)
- [<span data-ttu-id="f3728-123">Fusion 構造体</span><span class="sxs-lookup"><span data-stu-id="f3728-123">Fusion Structures</span></span>](fusion-structures.md)
