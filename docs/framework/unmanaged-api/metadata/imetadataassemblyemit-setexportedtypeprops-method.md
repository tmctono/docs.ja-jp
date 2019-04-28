---
title: IMetaDataAssemblyEmit::SetExportedTypeProps メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetExportedTypeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetExportedTypeProps
helpviewer_keywords:
- SetExportedTypeProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetExportedTypeProps method [.NET Framework metadata]
ms.assetid: 1c090153-fd5f-46c7-9cff-39a78d992c8f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5c09140488730179616d11932faa3542f704958a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61905178"
---
# <a name="imetadataassemblyemitsetexportedtypeprops-method"></a><span data-ttu-id="242ba-102">IMetaDataAssemblyEmit::SetExportedTypeProps メソッド</span><span class="sxs-lookup"><span data-stu-id="242ba-102">IMetaDataAssemblyEmit::SetExportedTypeProps Method</span></span>
<span data-ttu-id="242ba-103">指定された `ExportedType` メタデータ構造体を変更します。</span><span class="sxs-lookup"><span data-stu-id="242ba-103">Modifies the specified `ExportedType` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="242ba-104">構文</span><span class="sxs-lookup"><span data-stu-id="242ba-104">Syntax</span></span>  
  
```  
HRESULT SetExportedTypeProps (  
    [in] mdExportedType   ct,   
    [in] mdToken          tkImplementation,  
    [in] mdTypeDef        tkTypeDef,  
    [in] DWORD            dwExportedTypeFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="242ba-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="242ba-105">Parameters</span></span>  
 `ct`  
 <span data-ttu-id="242ba-106">[in]メタデータ トークンを指定する、`ExportedType`メタデータ構造を変更します。</span><span class="sxs-lookup"><span data-stu-id="242ba-106">[in] The metadata token that specifies the `ExportedType` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="242ba-107">[in]型のトークン`File`、 `AssemblyRef`、または`ExportedType`、この型を実装する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="242ba-107">[in] The token, of type `File`, `AssemblyRef`, or `ExportedType`, that specifies how this type is implemented.</span></span>  
  
 `tkTypeDef`  
 <span data-ttu-id="242ba-108">[in]`TypeDef`コード ファイルで参照されているトークンです。</span><span class="sxs-lookup"><span data-stu-id="242ba-108">[in] The `TypeDef` token referenced in the code file.</span></span>  
  
 `dwExportedTypeFlags`  
 <span data-ttu-id="242ba-109">[in]型の属性を指定する値のビットごとの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="242ba-109">[in] A bitwise combination of values that specify attributes of the type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="242ba-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="242ba-110">Remarks</span></span>  
 <span data-ttu-id="242ba-111">作成する、`ExportedType`メタデータ構造体を使用して、 [imetadataassemblyemit::defineexportedtype](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="242ba-111">To create an `ExportedType` metadata structure, use the [IMetaDataAssemblyEmit::DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="242ba-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="242ba-112">Requirements</span></span>  
 <span data-ttu-id="242ba-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="242ba-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="242ba-114">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="242ba-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="242ba-115">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="242ba-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="242ba-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="242ba-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="242ba-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="242ba-117">See also</span></span>

- [<span data-ttu-id="242ba-118">IMetaDataAssemblyEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="242ba-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
