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
ms.openlocfilehash: de1646cdbc11369b43a821d8b762879d1df7ed2e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751533"
---
# <a name="identityattribute-structure"></a><span data-ttu-id="d676a-102">IDENTITY_ATTRIBUTE 構造体</span><span class="sxs-lookup"><span data-stu-id="d676a-102">IDENTITY_ATTRIBUTE Structure</span></span>
<span data-ttu-id="d676a-103">メタデータ属性について説明する[IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)インスタンス。</span><span class="sxs-lookup"><span data-stu-id="d676a-103">Contains metadata attribute information about an [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d676a-104">構文</span><span class="sxs-lookup"><span data-stu-id="d676a-104">Syntax</span></span>  
  
```cpp  
typedef struct _IDENTITY_ATTRIBUTE {  
    LPCWSTR  pszNamespace;  
    LPCWSTR  pszName;  
    LPCWSTR  pszValue;  
} IDENTITY_ATTRIBUTE;  
```  
  
## <a name="members"></a><span data-ttu-id="d676a-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="d676a-105">Members</span></span>  
  
|<span data-ttu-id="d676a-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="d676a-106">Member</span></span>|<span data-ttu-id="d676a-107">説明</span><span class="sxs-lookup"><span data-stu-id="d676a-107">Description</span></span>|  
|------------|-----------------|  
|`pszNamespace`|<span data-ttu-id="d676a-108">属性はで、名前空間を含む null で終わる文字列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="d676a-108">A pointer to a null-terminated character string that contains the namespace the attribute is in.</span></span>|  
|`pszName`|<span data-ttu-id="d676a-109">属性の名前を含む null で終わる文字列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="d676a-109">A pointer to a null-terminated character string that contains the name of the attribute.</span></span>|  
|`pszValue`|<span data-ttu-id="d676a-110">属性の値を含む null で終わる文字列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="d676a-110">A pointer to a null-terminated character string that contains the value of the attribute.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d676a-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="d676a-111">Remarks</span></span>  
 <span data-ttu-id="d676a-112">`IDENTITY_ATTRIBUTE`構造体が null で終わる文字列への 3 つのポインターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d676a-112">The `IDENTITY_ATTRIBUTE` structure contains three pointers to null-terminated character strings.</span></span> <span data-ttu-id="d676a-113">これら 3 つの文字列には、1 つの属性について説明します。</span><span class="sxs-lookup"><span data-stu-id="d676a-113">These three strings describe one attribute.</span></span>  
  
 <span data-ttu-id="d676a-114">インスタンス、`IDENTITY_ATTRIBUTE`構造のインスタンスに関連付け、 [IDENTITY_ATTRIBUTE_BLOB](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md)構造体。</span><span class="sxs-lookup"><span data-stu-id="d676a-114">An instance of an `IDENTITY_ATTRIBUTE` structure is associated with an instance of an [IDENTITY_ATTRIBUTE_BLOB](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md) structure.</span></span> <span data-ttu-id="d676a-115">`IDENTITY_ATTRIBUTE`実際の文字列と、対応する構造に含まれる`IDENTITY_ATTRIBUTE_BLOB`構造で表示されている 3 つの文字列にオフセットを一覧表示、`IDENTITY_ATTRIBUTE`構造体。</span><span class="sxs-lookup"><span data-stu-id="d676a-115">The `IDENTITY_ATTRIBUTE` structure contains the actual strings, and the corresponding `IDENTITY_ATTRIBUTE_BLOB` structure lists the offsets to the three strings listed in the `IDENTITY_ATTRIBUTE` structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d676a-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="d676a-116">Requirements</span></span>  
 <span data-ttu-id="d676a-117">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d676a-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d676a-118">**ヘッダー:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="d676a-118">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="d676a-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d676a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d676a-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="d676a-120">See also</span></span>

- [<span data-ttu-id="d676a-121">IDefinitionIdentity インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d676a-121">IDefinitionIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)
- [<span data-ttu-id="d676a-122">IDENTITY_ATTRIBUTE_BLOB 構造体</span><span class="sxs-lookup"><span data-stu-id="d676a-122">IDENTITY_ATTRIBUTE_BLOB Structure</span></span>](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md)
- [<span data-ttu-id="d676a-123">Fusion 構造体</span><span class="sxs-lookup"><span data-stu-id="d676a-123">Fusion Structures</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)
