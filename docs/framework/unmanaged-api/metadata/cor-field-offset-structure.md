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
ms.openlocfilehash: 70fb637cd1edf81be140b0e3306e3b0a483653a6
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007989"
---
# <a name="cor_field_offset-structure"></a><span data-ttu-id="41464-102">COR_FIELD_OFFSET 構造体</span><span class="sxs-lookup"><span data-stu-id="41464-102">COR_FIELD_OFFSET Structure</span></span>
<span data-ttu-id="41464-103">指定したフィールドのクラス内の相対位置を格納します。</span><span class="sxs-lookup"><span data-stu-id="41464-103">Stores the offset, within a class, of the specified field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41464-104">構文</span><span class="sxs-lookup"><span data-stu-id="41464-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_FIELD_OFFSET {  
    mdFieldDef  ridOfField;  
    ULONG       ulOffset;  
} COR_FIELD_OFFSET;  
```  
  
## <a name="members"></a><span data-ttu-id="41464-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="41464-105">Members</span></span>  
  
|<span data-ttu-id="41464-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="41464-106">Member</span></span>|<span data-ttu-id="41464-107">説明</span><span class="sxs-lookup"><span data-stu-id="41464-107">Description</span></span>|  
|------------|-----------------|  
|`ridOfField`|<span data-ttu-id="41464-108">`mdFieldDef`フィールドを表すメタデータトークン。</span><span class="sxs-lookup"><span data-stu-id="41464-108">An `mdFieldDef` metadata token that represents the field.</span></span>|  
|`ulOffset`|<span data-ttu-id="41464-109">クラス内のフィールドのオフセット。</span><span class="sxs-lookup"><span data-stu-id="41464-109">The field's offset within its class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="41464-110">コメント</span><span class="sxs-lookup"><span data-stu-id="41464-110">Remarks</span></span>  
 <span data-ttu-id="41464-111">[IMetaDataImport:: GetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getclasslayout-method.md)メソッドと[IMetaDataEmit:: SetClassLayout](imetadataemit-setclasslayout-method.md)メソッドは、型のパラメーターを受け取り `COR_FIELD_OFFSET` ます。</span><span class="sxs-lookup"><span data-stu-id="41464-111">[IMetaDataImport::GetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getclasslayout-method.md) and [IMetaDataEmit::SetClassLayout](imetadataemit-setclasslayout-method.md) methods take a parameter of type `COR_FIELD_OFFSET`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41464-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="41464-112">Requirements</span></span>  
 <span data-ttu-id="41464-113">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41464-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41464-114">**ヘッダー:** CorHdr .h、Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="41464-114">**Header:** CorHdr.h, CorProf.idl</span></span>  
  
 <span data-ttu-id="41464-115">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41464-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41464-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="41464-116">See also</span></span>

- [<span data-ttu-id="41464-117">メタデータ構造体</span><span class="sxs-lookup"><span data-stu-id="41464-117">Metadata Structures</span></span>](metadata-structures.md)
- [<span data-ttu-id="41464-118">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="41464-118">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="41464-119">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="41464-119">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
