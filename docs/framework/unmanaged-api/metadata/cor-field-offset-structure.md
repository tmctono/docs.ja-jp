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
ms.openlocfilehash: 8cc803e3cf1442d324bf2eed0a37d0d236acd86d
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493059"
---
# <a name="cor_field_offset-structure"></a><span data-ttu-id="7dc39-102">COR_FIELD_OFFSET 構造体</span><span class="sxs-lookup"><span data-stu-id="7dc39-102">COR_FIELD_OFFSET Structure</span></span>
<span data-ttu-id="7dc39-103">指定したフィールドのクラス内の相対位置を格納します。</span><span class="sxs-lookup"><span data-stu-id="7dc39-103">Stores the offset, within a class, of the specified field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7dc39-104">構文</span><span class="sxs-lookup"><span data-stu-id="7dc39-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_FIELD_OFFSET {  
    mdFieldDef  ridOfField;  
    ULONG       ulOffset;  
} COR_FIELD_OFFSET;  
```  
  
## <a name="members"></a><span data-ttu-id="7dc39-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="7dc39-105">Members</span></span>  
  
|<span data-ttu-id="7dc39-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="7dc39-106">Member</span></span>|<span data-ttu-id="7dc39-107">説明</span><span class="sxs-lookup"><span data-stu-id="7dc39-107">Description</span></span>|  
|------------|-----------------|  
|`ridOfField`|<span data-ttu-id="7dc39-108">`mdFieldDef`フィールドを表すメタデータトークン。</span><span class="sxs-lookup"><span data-stu-id="7dc39-108">An `mdFieldDef` metadata token that represents the field.</span></span>|  
|`ulOffset`|<span data-ttu-id="7dc39-109">クラス内のフィールドのオフセット。</span><span class="sxs-lookup"><span data-stu-id="7dc39-109">The field's offset within its class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7dc39-110">解説</span><span class="sxs-lookup"><span data-stu-id="7dc39-110">Remarks</span></span>  
 <span data-ttu-id="7dc39-111">[IMetaDataImport:: GetClassLayout](imetadataimport-getclasslayout-method.md)メソッドと[IMetaDataEmit:: SetClassLayout](imetadataemit-setclasslayout-method.md)メソッドは、型のパラメーターを受け取り `COR_FIELD_OFFSET` ます。</span><span class="sxs-lookup"><span data-stu-id="7dc39-111">[IMetaDataImport::GetClassLayout](imetadataimport-getclasslayout-method.md) and [IMetaDataEmit::SetClassLayout](imetadataemit-setclasslayout-method.md) methods take a parameter of type `COR_FIELD_OFFSET`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7dc39-112">要件</span><span class="sxs-lookup"><span data-stu-id="7dc39-112">Requirements</span></span>  
 <span data-ttu-id="7dc39-113">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7dc39-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7dc39-114">**ヘッダー:** CorHdr .h、Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="7dc39-114">**Header:** CorHdr.h, CorProf.idl</span></span>  
  
 <span data-ttu-id="7dc39-115">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7dc39-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7dc39-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="7dc39-116">See also</span></span>

- [<span data-ttu-id="7dc39-117">メタデータ構造体</span><span class="sxs-lookup"><span data-stu-id="7dc39-117">Metadata Structures</span></span>](metadata-structures.md)
- [<span data-ttu-id="7dc39-118">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7dc39-118">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="7dc39-119">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7dc39-119">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
