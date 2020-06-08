---
title: IMetaDataImport::EnumFields メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumFields
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumFields
helpviewer_keywords:
- EnumFields method [.NET Framework metadata]
- IMetaDataImport::EnumFields method [.NET Framework metadata]
ms.assetid: 1d23247e-c58c-45db-afd8-83aa89cde18e
topic_type:
- apiref
ms.openlocfilehash: 1ff2dd64dc4797bc485550c30f7204644a3adb47
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492279"
---
# <a name="imetadataimportenumfields-method"></a><span data-ttu-id="77c74-102">IMetaDataImport::EnumFields メソッド</span><span class="sxs-lookup"><span data-stu-id="77c74-102">IMetaDataImport::EnumFields Method</span></span>
<span data-ttu-id="77c74-103">指定した TypeDef トークンによって参照される型の FieldDef トークンを列挙します。</span><span class="sxs-lookup"><span data-stu-id="77c74-103">Enumerates FieldDef tokens for the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77c74-104">構文</span><span class="sxs-lookup"><span data-stu-id="77c74-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumFields (
   [in, out] HCORENUM    *phEnum,
   [in]      mdTypeDef   cl,
   [out]     mdFieldDef  rFields[],
   [in]      ULONG       cMax,
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="77c74-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="77c74-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="77c74-106">[入力、出力]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="77c74-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="77c74-107">からフィールドを列挙するクラスの TypeDef トークン。</span><span class="sxs-lookup"><span data-stu-id="77c74-107">[in] The TypeDef token of the class whose fields are to be enumerated.</span></span>  
  
 `rFields`  
 <span data-ttu-id="77c74-108">入出力FieldDef トークンの一覧。</span><span class="sxs-lookup"><span data-stu-id="77c74-108">[out] The list of FieldDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="77c74-109">[in] `rFields` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="77c74-109">[in] The maximum size of the `rFields` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="77c74-110">入出力で返された FieldDef トークンの実際の数 `rFields` 。</span><span class="sxs-lookup"><span data-stu-id="77c74-110">[out] The actual number of FieldDef tokens returned in `rFields`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="77c74-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="77c74-111">Return Value</span></span>  
  
|<span data-ttu-id="77c74-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="77c74-112">HRESULT</span></span>|<span data-ttu-id="77c74-113">説明</span><span class="sxs-lookup"><span data-stu-id="77c74-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="77c74-114">`EnumFields`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="77c74-114">`EnumFields` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="77c74-115">列挙するフィールドがありません。</span><span class="sxs-lookup"><span data-stu-id="77c74-115">There are no fields to enumerate.</span></span> <span data-ttu-id="77c74-116">この場合、 `pcTokens` は0になります。</span><span class="sxs-lookup"><span data-stu-id="77c74-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="77c74-117">要件</span><span class="sxs-lookup"><span data-stu-id="77c74-117">Requirements</span></span>  
 <span data-ttu-id="77c74-118">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77c74-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77c74-119">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="77c74-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="77c74-120">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="77c74-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="77c74-121">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77c74-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77c74-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="77c74-122">See also</span></span>

- [<span data-ttu-id="77c74-123">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="77c74-123">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="77c74-124">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="77c74-124">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
