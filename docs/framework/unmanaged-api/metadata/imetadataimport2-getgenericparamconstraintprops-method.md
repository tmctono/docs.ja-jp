---
title: IMetaDataImport2::GetGenericParamConstraintProps メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetGenericParamConstraintProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetGenericParamConstraintProps
helpviewer_keywords:
- IMetaDataImport2::GetGenericParamConstraintProps method [.NET Framework metadata]
- GetGenericParamConstraintProps method [.NET Framework metadata]
ms.assetid: c5fee4a0-b132-4e5e-8730-e586ce314b9a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e0503c5bd924793df8143c89e358618fb8844c6c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59215119"
---
# <a name="imetadataimport2getgenericparamconstraintprops-method"></a><span data-ttu-id="b226b-102">IMetaDataImport2::GetGenericParamConstraintProps メソッド</span><span class="sxs-lookup"><span data-stu-id="b226b-102">IMetaDataImport2::GetGenericParamConstraintProps Method</span></span>
<span data-ttu-id="b226b-103">指定した制約トークンによって表されるジェネリック パラメーターの制約に関連付けられているメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="b226b-103">Gets the metadata associated with the generic parameter constraint represented by the specified constraint token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b226b-104">構文</span><span class="sxs-lookup"><span data-stu-id="b226b-104">Syntax</span></span>  
  
```  
HRESULT GetGenericParamConstraintProps (  
   [in]  mdGenericParamConstraint  gpc,  
   [out] mdGenericParam            *ptGenericParam,  
   [out] mdToken                   *ptkConstraintType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b226b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b226b-105">Parameters</span></span>  
 `gpc`  
 <span data-ttu-id="b226b-106">[in]メタデータを返すジェネリック パラメーターの制約にトークンです。</span><span class="sxs-lookup"><span data-stu-id="b226b-106">[in] The token to the generic parameter constraint for which to return the metadata.</span></span>  
  
 `ptGenericParam`  
 <span data-ttu-id="b226b-107">[out]制約されているジェネリック パラメーターを表すトークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="b226b-107">[out] A pointer to the token that represents the generic parameter that is constrained.</span></span>  
  
 `ptkConstraintType`  
 <span data-ttu-id="b226b-108">[out]上の制約を表す TypeDef、TypeRef、または TypeSpec トークンへのポインター`ptGenericParam`します。</span><span class="sxs-lookup"><span data-stu-id="b226b-108">[out] A pointer to a TypeDef, TypeRef, or TypeSpec token that represents a constraint on `ptGenericParam`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b226b-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="b226b-109">Requirements</span></span>  
 <span data-ttu-id="b226b-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b226b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b226b-111">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b226b-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b226b-112">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="b226b-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b226b-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b226b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b226b-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="b226b-114">See also</span></span>

- [<span data-ttu-id="b226b-115">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b226b-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="b226b-116">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b226b-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
