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
ms.openlocfilehash: ae682c354a7a5188611b103008a3e18f8d821260
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431943"
---
# <a name="imetadataassemblyemitsetexportedtypeprops-method"></a><span data-ttu-id="923d1-102">IMetaDataAssemblyEmit::SetExportedTypeProps メソッド</span><span class="sxs-lookup"><span data-stu-id="923d1-102">IMetaDataAssemblyEmit::SetExportedTypeProps Method</span></span>
<span data-ttu-id="923d1-103">指定された `ExportedType` メタデータ構造体を変更します。</span><span class="sxs-lookup"><span data-stu-id="923d1-103">Modifies the specified `ExportedType` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="923d1-104">構文</span><span class="sxs-lookup"><span data-stu-id="923d1-104">Syntax</span></span>  
  
```cpp  
HRESULT SetExportedTypeProps (  
    [in] mdExportedType   ct,   
    [in] mdToken          tkImplementation,  
    [in] mdTypeDef        tkTypeDef,  
    [in] DWORD            dwExportedTypeFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="923d1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="923d1-105">Parameters</span></span>  
 `ct`  
 <span data-ttu-id="923d1-106">から変更する `ExportedType` メタデータ構造を指定するメタデータトークン。</span><span class="sxs-lookup"><span data-stu-id="923d1-106">[in] The metadata token that specifies the `ExportedType` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="923d1-107">からこの型の実装方法を指定する `File`、`AssemblyRef`、または `ExportedType`型のトークン。</span><span class="sxs-lookup"><span data-stu-id="923d1-107">[in] The token, of type `File`, `AssemblyRef`, or `ExportedType`, that specifies how this type is implemented.</span></span>  
  
 `tkTypeDef`  
 <span data-ttu-id="923d1-108">からコードファイルで参照される `TypeDef` トークン。</span><span class="sxs-lookup"><span data-stu-id="923d1-108">[in] The `TypeDef` token referenced in the code file.</span></span>  
  
 `dwExportedTypeFlags`  
 <span data-ttu-id="923d1-109">から型の属性を指定する値のビットごとの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="923d1-109">[in] A bitwise combination of values that specify attributes of the type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="923d1-110">コメント</span><span class="sxs-lookup"><span data-stu-id="923d1-110">Remarks</span></span>  
 <span data-ttu-id="923d1-111">`ExportedType` メタデータ構造を作成するには、 [IMetaDataAssemblyEmit::D efineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md)メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="923d1-111">To create an `ExportedType` metadata structure, use the [IMetaDataAssemblyEmit::DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="923d1-112">要件</span><span class="sxs-lookup"><span data-stu-id="923d1-112">Requirements</span></span>  
 <span data-ttu-id="923d1-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="923d1-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="923d1-114">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="923d1-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="923d1-115">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="923d1-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="923d1-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="923d1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="923d1-117">参照</span><span class="sxs-lookup"><span data-stu-id="923d1-117">See also</span></span>

- [<span data-ttu-id="923d1-118">IMetaDataAssemblyEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="923d1-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
