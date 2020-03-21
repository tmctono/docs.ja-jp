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
ms.openlocfilehash: 6825a5198976cc7ab2c04ebd6e782418dcf4a8f7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177677"
---
# <a name="imetadataemitdefineimporttype-method"></a><span data-ttu-id="43a98-102">IMetaDataEmit::DefineImportType メソッド</span><span class="sxs-lookup"><span data-stu-id="43a98-102">IMetaDataEmit::DefineImportType Method</span></span>
<span data-ttu-id="43a98-103">現在のスコープの外部で定義されている指定した型への参照を作成し、その参照のトークンを定義します。</span><span class="sxs-lookup"><span data-stu-id="43a98-103">Creates a reference to the specified type that is defined outside the current scope, and defines a token for that reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43a98-104">構文</span><span class="sxs-lookup"><span data-stu-id="43a98-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="43a98-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="43a98-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="43a98-106">[in]ターゲット型のインポート元のアセンブリを表す[IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="43a98-106">[in] An [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface that represents the assembly from which the target type is imported.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="43a98-107">[in]で指定されたアセンブリのハッシュを格納する`pAssemImport`配列。</span><span class="sxs-lookup"><span data-stu-id="43a98-107">[in] An array that contains the hash for the assembly specified by `pAssemImport`.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="43a98-108">[in] `pbHashValue` 配列のバイト数。</span><span class="sxs-lookup"><span data-stu-id="43a98-108">[in] The number of bytes in the `pbHashValue` array.</span></span>  
  
 `pImport`  
 <span data-ttu-id="43a98-109">[in]ターゲット型のインポート元のメタデータ スコープを表す[IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="43a98-109">[in] An [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface that represents the metadata scope from which the target type is imported.</span></span>  
  
 `tdImport`  
 <span data-ttu-id="43a98-110">[in]ターゲット`mdTypeDef`の型を指定するトークン。</span><span class="sxs-lookup"><span data-stu-id="43a98-110">[in] An `mdTypeDef` token that specifies the target type.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="43a98-111">[in]ターゲット型のインポート先のアセンブリを表す[IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="43a98-111">[in] An [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) interface that represents the assembly into which the target type is imported.</span></span>  
  
 `ptr`  
 <span data-ttu-id="43a98-112">[アウト]型`mdTypeRef`参照の現在のスコープで定義されているトークン。</span><span class="sxs-lookup"><span data-stu-id="43a98-112">[out] The `mdTypeRef` token that is defined in the current scope for the type reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43a98-113">解説</span><span class="sxs-lookup"><span data-stu-id="43a98-113">Remarks</span></span>  
 <span data-ttu-id="43a98-114">[:D メソッド](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md)を呼び出す前に、`DefineImportType`メソッドを使用して、メンバーの親クラスまたは親インターフェイスの現在のスコープ内の型参照を作成できます。</span><span class="sxs-lookup"><span data-stu-id="43a98-114">Prior to calling the [IMetaDataEmit::DefineImportMember](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md) method, you can use the `DefineImportType` method to create a type reference, in the current scope, for the member's parent class or parent interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43a98-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="43a98-115">Requirements</span></span>  
 <span data-ttu-id="43a98-116">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43a98-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43a98-117">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="43a98-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="43a98-118">**ライブラリ:** MSCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="43a98-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="43a98-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43a98-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43a98-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="43a98-120">See also</span></span>

- [<span data-ttu-id="43a98-121">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="43a98-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="43a98-122">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="43a98-122">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
