---
title: IMetaDataEmit::DefineImportType メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineImportType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineImportType
helpviewer_keywords:
- DefineImportType method [.NET Framework metadata]
- IMetaDataEmit::DefineImportType method [.NET Framework metadata]
ms.assetid: 37fd27af-8062-4904-ace4-51bb78ec600a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c9debf041a26af128dea3cde214630f5a95eac71
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992538"
---
# <a name="imetadataemitdefineimporttype-method"></a><span data-ttu-id="d7ebf-102">IMetaDataEmit::DefineImportType メソッド</span><span class="sxs-lookup"><span data-stu-id="d7ebf-102">IMetaDataEmit::DefineImportType Method</span></span>
<span data-ttu-id="d7ebf-103">現在のスコープ外に定義され、その参照のトークンを定義する指定した型への参照を作成します。</span><span class="sxs-lookup"><span data-stu-id="d7ebf-103">Creates a reference to the specified type that is defined outside the current scope, and defines a token for that reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7ebf-104">構文</span><span class="sxs-lookup"><span data-stu-id="d7ebf-104">Syntax</span></span>  
  
```  
HRESULT DefineImportType (   
    [in]  IMetaDataAssemblyImport  *pAssemImport,   
    [in]  const void               *pbHashValue,   
    [in]  ULONG                    cbHashValue,    
    [in]  IMetaDataImport          *pImport,   
    [in]  mdTypeDef                tdImport,   
    [in]  IMetaDataAssemblyEmit    *pAssemEmit,   
    [out] mdTypeRef                *ptr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7ebf-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d7ebf-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="d7ebf-106">[in][IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)ターゲットの種類のインポート元となるアセンブリを表すインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="d7ebf-106">[in] An [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface that represents the assembly from which the target type is imported.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="d7ebf-107">[in]指定されたアセンブリのハッシュを格納する配列`pAssemImport`します。</span><span class="sxs-lookup"><span data-stu-id="d7ebf-107">[in] An array that contains the hash for the assembly specified by `pAssemImport`.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="d7ebf-108">[in] `pbHashValue` 配列のバイト数。</span><span class="sxs-lookup"><span data-stu-id="d7ebf-108">[in] The number of bytes in the `pbHashValue` array.</span></span>  
  
 `pImport`  
 <span data-ttu-id="d7ebf-109">[in][IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)ターゲットの種類のインポート元のメタデータ スコープを表すインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="d7ebf-109">[in] An [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface that represents the metadata scope from which the target type is imported.</span></span>  
  
 `tdImport`  
 <span data-ttu-id="d7ebf-110">[in]`mdTypeDef`対象の型を示すトークン。</span><span class="sxs-lookup"><span data-stu-id="d7ebf-110">[in] An `mdTypeDef` token that specifies the target type.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="d7ebf-111">[in][IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)ターゲットの種類のインポート先のアセンブリを表すインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="d7ebf-111">[in] An [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) interface that represents the assembly into which the target type is imported.</span></span>  
  
 `ptr`  
 <span data-ttu-id="d7ebf-112">[out]`mdTypeRef`型参照の現在のスコープで定義されているトークンです。</span><span class="sxs-lookup"><span data-stu-id="d7ebf-112">[out] The `mdTypeRef` token that is defined in the current scope for the type reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7ebf-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="d7ebf-113">Remarks</span></span>  
 <span data-ttu-id="d7ebf-114">呼び出しの前に、 [imetadataemit::defineimportmember](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md)メソッドが使用できる、`DefineImportType`メンバーの親クラスまたは親インターフェイスの現在のスコープ内の型の参照を作成します。</span><span class="sxs-lookup"><span data-stu-id="d7ebf-114">Prior to calling the [IMetaDataEmit::DefineImportMember](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md) method, you can use the `DefineImportType` method to create a type reference, in the current scope, for the member's parent class or parent interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7ebf-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="d7ebf-115">Requirements</span></span>  
 <span data-ttu-id="d7ebf-116">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7ebf-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7ebf-117">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d7ebf-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d7ebf-118">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="d7ebf-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d7ebf-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7ebf-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7ebf-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="d7ebf-120">See also</span></span>

- [<span data-ttu-id="d7ebf-121">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d7ebf-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="d7ebf-122">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d7ebf-122">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
