---
title: IMetaDataAssemblyEmit::DefineExportedType メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineExportedType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineExportedType
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineExportedType method [.NET Framework metadata]
- DefineExportedType method [.NET Framework metadata]
ms.assetid: fad01d7a-3178-4c8c-9f0a-4641e3701c9b
topic_type:
- apiref
ms.openlocfilehash: 388f227377ddf73fe1297e1c777bb1c0607c13d2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177877"
---
# <a name="imetadataassemblyemitdefineexportedtype-method"></a><span data-ttu-id="e3290-102">IMetaDataAssemblyEmit::DefineExportedType メソッド</span><span class="sxs-lookup"><span data-stu-id="e3290-102">IMetaDataAssemblyEmit::DefineExportedType Method</span></span>
<span data-ttu-id="e3290-103">指定してエクスポートした型のメタデータが含まれる `ExportedType` 構造体を作成し、関連付けられたメタデータ トークンを返します。</span><span class="sxs-lookup"><span data-stu-id="e3290-103">Creates an `ExportedType` structure containing metadata for the specified exported type, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3290-104">構文</span><span class="sxs-lookup"><span data-stu-id="e3290-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineExportedType (  
    [in]  LPCWSTR             szName,  
    [in]  mdToken             tkImplementation,
    [in]  mdTypeDef           tkTypeDef,  
    [in]  DWORD               dwExportedTypeFlags,  
    [out] mdExportedType      *pmdct  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e3290-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e3290-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="e3290-106">[in]エクスポートする型の名前。</span><span class="sxs-lookup"><span data-stu-id="e3290-106">[in] The name of type to be exported.</span></span> <span data-ttu-id="e3290-107">共通言語ランタイムのバージョン 1.1 の場合、エクスポートされる型の名前は、型の で`TypeDef`指定された名前と完全に一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3290-107">For version 1.1 of the common language runtime, the name of the exported type must exactly match the name given in the `TypeDef` for the type.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="e3290-108">[in]エクスポートされた型が実装される場所を指定するトークン。</span><span class="sxs-lookup"><span data-stu-id="e3290-108">[in] A token specifying where the exported type is implemented.</span></span> <span data-ttu-id="e3290-109">有効な値と、関連する意味は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e3290-109">The valid values and their associated meanings are:</span></span>  
  
- <span data-ttu-id="e3290-110">`mdFile`型は、このアセンブリ内の別のファイルに実装されます。</span><span class="sxs-lookup"><span data-stu-id="e3290-110">`mdFile` The type is implemented in a different file within this assembly.</span></span>  
  
- <span data-ttu-id="e3290-111">`mdAssemblyRef`型は別のアセンブリに実装されています。</span><span class="sxs-lookup"><span data-stu-id="e3290-111">`mdAssemblyRef` The type is implemented in a different assembly.</span></span>  
  
- <span data-ttu-id="e3290-112">`mdExportedTYpe`型は他の型内で入れ子になります。</span><span class="sxs-lookup"><span data-stu-id="e3290-112">`mdExportedTYpe` The type is nested within some other type.</span></span>  
  
- <span data-ttu-id="e3290-113">`mdFileNil`型はマニフェストと同じファイルにあり、入れ子になった型ではありません。</span><span class="sxs-lookup"><span data-stu-id="e3290-113">`mdFileNil` The type is in the same file as the manifest and is not a nested type.</span></span>  
  
 `tkTypeDef`  
 <span data-ttu-id="e3290-114">[in]エクスポートする型を指定するメタデータへのトークン。</span><span class="sxs-lookup"><span data-stu-id="e3290-114">[in] A token to the metadata that specifies the type to be exported.</span></span> <span data-ttu-id="e3290-115">この値は、型を`TypeDef`実装するファイルのテーブルに入力され、そのファイルがこのアセンブリ内にある場合にのみ関連します。</span><span class="sxs-lookup"><span data-stu-id="e3290-115">This value is entered in the `TypeDef` table in the file that implements the type and is relevant only if that file is in this assembly.</span></span>  
  
 `dwExportedTypeFlags`  
 <span data-ttu-id="e3290-116">[in]エクスポートされた型のプロパティ設定を定義する[CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md)列挙値のビットごとの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="e3290-116">[in] A bitwise combination of [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) enumeration values that define the property settings for the exported type.</span></span>  
  
 `pmdct`  
 <span data-ttu-id="e3290-117">[アウト]エクスポートされた型を示す、返されたメタデータ トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="e3290-117">[out] A pointer to the returned metadata token that indicates the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e3290-118">解説</span><span class="sxs-lookup"><span data-stu-id="e3290-118">Remarks</span></span>  
 <span data-ttu-id="e3290-119">メタデータ`ExportedType`構造は、このアセンブリによって公開され、マニフェストを含むモジュール以外のモジュールに実装される型ごとに定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3290-119">An `ExportedType` metadata structure must be defined for each type that is exposed by this assembly and that is implemented in a module other than the one containing the manifest.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3290-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="e3290-120">Requirements</span></span>  
 <span data-ttu-id="e3290-121">**プラットフォーム:**[「システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3290-121">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3290-122">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="e3290-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e3290-123">**ライブラリ:** MsCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="e3290-123">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e3290-124">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3290-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3290-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="e3290-125">See also</span></span>

- [<span data-ttu-id="e3290-126">IMetaDataAssemblyEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e3290-126">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
