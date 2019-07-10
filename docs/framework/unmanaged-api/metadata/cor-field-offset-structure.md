---
title: COR_FIELD_OFFSET 構造体
ms.date: 03/30/2017
api_name:
- COR_FIELD_OFFSET
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_FIELD_OFFSET
helpviewer_keywords:
- COR_FIELD_OFFSET structure [.NET Framework metadata]
ms.assetid: cced5298-277f-4a5a-8ecf-a0050c1096ea
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fdfbb22d231d16be7757ff5df26a5a010928af54
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767054"
---
# <a name="corfieldoffset-structure"></a><span data-ttu-id="21ea0-102">COR_FIELD_OFFSET 構造体</span><span class="sxs-lookup"><span data-stu-id="21ea0-102">COR_FIELD_OFFSET Structure</span></span>
<span data-ttu-id="21ea0-103">指定したフィールドのクラス内の相対位置を格納します。</span><span class="sxs-lookup"><span data-stu-id="21ea0-103">Stores the offset, within a class, of the specified field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21ea0-104">構文</span><span class="sxs-lookup"><span data-stu-id="21ea0-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_FIELD_OFFSET {  
    mdFieldDef  ridOfField;  
    ULONG       ulOffset;  
} COR_FIELD_OFFSET;  
```  
  
## <a name="members"></a><span data-ttu-id="21ea0-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="21ea0-105">Members</span></span>  
  
|<span data-ttu-id="21ea0-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="21ea0-106">Member</span></span>|<span data-ttu-id="21ea0-107">説明</span><span class="sxs-lookup"><span data-stu-id="21ea0-107">Description</span></span>|  
|------------|-----------------|  
|`ridOfField`|<span data-ttu-id="21ea0-108">`mdFieldDef`フィールドを表すメタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="21ea0-108">An `mdFieldDef` metadata token that represents the field.</span></span>|  
|`ulOffset`|<span data-ttu-id="21ea0-109">そのクラス内のフィールドをオフセットします。</span><span class="sxs-lookup"><span data-stu-id="21ea0-109">The field's offset within its class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="21ea0-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="21ea0-110">Remarks</span></span>  
 <span data-ttu-id="21ea0-111">[Imetadataimport::getclasslayout](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getclasslayout-method.md)と[imetadataemit::setclasslayout](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setclasslayout-method.md)メソッドは、型のパラメーターを受け取る`COR_FIELD_OFFSET`します。</span><span class="sxs-lookup"><span data-stu-id="21ea0-111">[IMetaDataImport::GetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getclasslayout-method.md) and [IMetaDataEmit::SetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setclasslayout-method.md) methods take a parameter of type `COR_FIELD_OFFSET`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21ea0-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="21ea0-112">Requirements</span></span>  
 <span data-ttu-id="21ea0-113">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="21ea0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21ea0-114">**ヘッダー:** CorHdr.h, CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="21ea0-114">**Header:** CorHdr.h, CorProf.idl</span></span>  
  
 <span data-ttu-id="21ea0-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21ea0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21ea0-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="21ea0-116">See also</span></span>

- [<span data-ttu-id="21ea0-117">メタデータ構造体</span><span class="sxs-lookup"><span data-stu-id="21ea0-117">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [<span data-ttu-id="21ea0-118">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="21ea0-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="21ea0-119">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="21ea0-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
