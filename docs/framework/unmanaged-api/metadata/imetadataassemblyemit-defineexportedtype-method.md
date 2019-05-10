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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5702fac139ba602828bb8722a1e3e25d6f1c58f6
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64625435"
---
# <a name="imetadataassemblyemitdefineexportedtype-method"></a><span data-ttu-id="09d29-102">IMetaDataAssemblyEmit::DefineExportedType メソッド</span><span class="sxs-lookup"><span data-stu-id="09d29-102">IMetaDataAssemblyEmit::DefineExportedType Method</span></span>
<span data-ttu-id="09d29-103">指定してエクスポートした型のメタデータが含まれる `ExportedType` 構造体を作成し、関連付けられたメタデータ トークンを返します。</span><span class="sxs-lookup"><span data-stu-id="09d29-103">Creates an `ExportedType` structure containing metadata for the specified exported type, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09d29-104">構文</span><span class="sxs-lookup"><span data-stu-id="09d29-104">Syntax</span></span>  
  
```  
HRESULT DefineExportedType (  
    [in]  LPCWSTR             szName,  
    [in]  mdToken             tkImplementation,   
    [in]  mdTypeDef           tkTypeDef,  
    [in]  DWORD               dwExportedTypeFlags,  
    [out] mdExportedType      *pmdct  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09d29-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="09d29-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="09d29-106">[in]エクスポートする型の名前。</span><span class="sxs-lookup"><span data-stu-id="09d29-106">[in] The name of type to be exported.</span></span> <span data-ttu-id="09d29-107">エクスポートされた型の名前、共通言語ランタイムのバージョン 1.1 で指定された名前と一致する必要がありますの`TypeDef`型。</span><span class="sxs-lookup"><span data-stu-id="09d29-107">For version 1.1 of the common language runtime, the name of the exported type must exactly match the name given in the `TypeDef` for the type.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="09d29-108">[in]エクスポートされる型が実装されているを指定するトークンです。</span><span class="sxs-lookup"><span data-stu-id="09d29-108">[in] A token specifying where the exported type is implemented.</span></span> <span data-ttu-id="09d29-109">有効な値とその意味は。</span><span class="sxs-lookup"><span data-stu-id="09d29-109">The valid values and their associated meanings are:</span></span>  
  
- <span data-ttu-id="09d29-110">`mdFile` 種類は、このアセンブリ内の別のファイルに実装されます。</span><span class="sxs-lookup"><span data-stu-id="09d29-110">`mdFile` The type is implemented in a different file within this assembly.</span></span>  
  
- <span data-ttu-id="09d29-111">`mdAssemblyRef` 種類は、別のアセンブリに実装されます。</span><span class="sxs-lookup"><span data-stu-id="09d29-111">`mdAssemblyRef` The type is implemented in a different assembly.</span></span>  
  
- <span data-ttu-id="09d29-112">`mdExportedTYpe` 型が他の何らかの種類内で入れ子になった。</span><span class="sxs-lookup"><span data-stu-id="09d29-112">`mdExportedTYpe` The type is nested within some other type.</span></span>  
  
- <span data-ttu-id="09d29-113">`mdFileNil` 種類は、マニフェストと同じファイルであり、入れ子になった型ではありません。</span><span class="sxs-lookup"><span data-stu-id="09d29-113">`mdFileNil` The type is in the same file as the manifest and is not a nested type.</span></span>  
  
 `tkTypeDef`  
 <span data-ttu-id="09d29-114">[in]エクスポートする型を指定するメタデータ トークンです。</span><span class="sxs-lookup"><span data-stu-id="09d29-114">[in] A token to the metadata that specifies the type to be exported.</span></span> <span data-ttu-id="09d29-115">この値が入力される、`TypeDef`内の型を実装、そのファイルがこのアセンブリ内にある場合にのみ関連するファイル内のテーブル。</span><span class="sxs-lookup"><span data-stu-id="09d29-115">This value is entered in the `TypeDef` table in the file that implements the type and is relevant only if that file is in this assembly.</span></span>  
  
 `dwExportedTypeFlags`  
 <span data-ttu-id="09d29-116">[in]ビットごとの組み合わせ[CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md)エクスポートされる型のプロパティの設定を定義する列挙値。</span><span class="sxs-lookup"><span data-stu-id="09d29-116">[in] A bitwise combination of [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) enumeration values that define the property settings for the exported type.</span></span>  
  
 `pmdct`  
 <span data-ttu-id="09d29-117">[out]エクスポートされた型を示す、返されたメタデータ トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="09d29-117">[out] A pointer to the returned metadata token that indicates the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="09d29-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="09d29-118">Remarks</span></span>  
 <span data-ttu-id="09d29-119">`ExportedType`このアセンブリによって公開されると、モジュール マニフェストを含む 1 つ以外で実装される各型のメタデータ構造を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09d29-119">An `ExportedType` metadata structure must be defined for each type that is exposed by this assembly and that is implemented in a module other than the one containing the manifest.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09d29-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="09d29-120">Requirements</span></span>  
 <span data-ttu-id="09d29-121">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="09d29-121">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09d29-122">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="09d29-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="09d29-123">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="09d29-123">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="09d29-124">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09d29-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09d29-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="09d29-125">See also</span></span>

- [<span data-ttu-id="09d29-126">IMetaDataAssemblyEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="09d29-126">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
