---
title: IMetaDataAssemblyImport::FindExportedTypeByName メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.FindExportedTypeByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::FindExportedTypeByName
helpviewer_keywords:
- FindExportedTypeByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindExportedTypeByName method [.NET Framework metadata]
ms.assetid: 46264b2c-574d-4dde-aafc-77187a104fdd
topic_type:
- apiref
ms.openlocfilehash: edfe5de9c9d7ef9607a2eea5146194bbd4393a92
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175994"
---
# <a name="imetadataassemblyimportfindexportedtypebyname-method"></a><span data-ttu-id="0697b-102">IMetaDataAssemblyImport::FindExportedTypeByName メソッド</span><span class="sxs-lookup"><span data-stu-id="0697b-102">IMetaDataAssemblyImport::FindExportedTypeByName Method</span></span>
<span data-ttu-id="0697b-103">名前と外側の型を指定して、エクスポートされた型へのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="0697b-103">Gets a pointer to an exported type, given its name and enclosing type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0697b-104">構文</span><span class="sxs-lookup"><span data-stu-id="0697b-104">Syntax</span></span>  
  
```cpp  
HRESULT FindExportedTypeByName (  
    [in]  LPCWSTR           szName,
    [in]  mdToken           mdtExportedType,
    [out] mdExportedType    *ptkExportedType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0697b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0697b-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="0697b-106">[in]エクスポートされた型の名前。</span><span class="sxs-lookup"><span data-stu-id="0697b-106">[in] The name of the exported type.</span></span>  
  
 `mdtExportedType`  
 <span data-ttu-id="0697b-107">[in]エクスポートされた型の外側のクラスのメタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="0697b-107">[in] The metadata token for the enclosing class of the exported type.</span></span> <span data-ttu-id="0697b-108">この値は`mdExportedTypeNil`、要求されたエクスポート型が入れ子にされた型でない場合です。</span><span class="sxs-lookup"><span data-stu-id="0697b-108">This value is `mdExportedTypeNil` if the requested exported type is not a nested type.</span></span>  
  
 `ptkExportedType`  
 <span data-ttu-id="0697b-109">[アウト]エクスポートされた型を`mdExportedType`表すトークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="0697b-109">[out] A pointer to the `mdExportedType` token that represents the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0697b-110">解説</span><span class="sxs-lookup"><span data-stu-id="0697b-110">Remarks</span></span>  
 <span data-ttu-id="0697b-111">この`FindExportedTypeByName`メソッドは、共通言語ランタイムで使用される標準規則を使用して参照を解決します。</span><span class="sxs-lookup"><span data-stu-id="0697b-111">The `FindExportedTypeByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0697b-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="0697b-112">Requirements</span></span>  
 <span data-ttu-id="0697b-113">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0697b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0697b-114">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="0697b-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0697b-115">**ライブラリ:** MsCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="0697b-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0697b-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0697b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0697b-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="0697b-117">See also</span></span>

- [<span data-ttu-id="0697b-118">IMetaDataAssemblyImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0697b-118">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="0697b-119">ランタイムがアセンブリを検索する方法</span><span class="sxs-lookup"><span data-stu-id="0697b-119">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
