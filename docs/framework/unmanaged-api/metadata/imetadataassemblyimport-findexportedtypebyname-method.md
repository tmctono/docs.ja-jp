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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 32a7b7b498cc4e52b8be3f43ae52293de380d9f7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59182261"
---
# <a name="imetadataassemblyimportfindexportedtypebyname-method"></a><span data-ttu-id="d67e4-102">IMetaDataAssemblyImport::FindExportedTypeByName メソッド</span><span class="sxs-lookup"><span data-stu-id="d67e4-102">IMetaDataAssemblyImport::FindExportedTypeByName Method</span></span>
<span data-ttu-id="d67e4-103">名前およびそれを囲む型を指定するエクスポートされた型、ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="d67e4-103">Gets a pointer to an exported type, given its name and enclosing type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d67e4-104">構文</span><span class="sxs-lookup"><span data-stu-id="d67e4-104">Syntax</span></span>  
  
```  
HRESULT FindExportedTypeByName (  
    [in]  LPCWSTR           szName,   
    [in]  mdToken           mdtExportedType,   
    [out] mdExportedType    *ptkExportedType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d67e4-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d67e4-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="d67e4-106">[in]エクスポートされる型の名前。</span><span class="sxs-lookup"><span data-stu-id="d67e4-106">[in] The name of the exported type.</span></span>  
  
 `mdtExportedType`  
 <span data-ttu-id="d67e4-107">[in]エクスポートされた型の外側のクラスのメタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="d67e4-107">[in] The metadata token for the enclosing class of the exported type.</span></span> <span data-ttu-id="d67e4-108">この値は`mdExportedTypeNil`型が入れ子になった型ではない場合は、要求されたエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="d67e4-108">This value is `mdExportedTypeNil` if the requested exported type is not a nested type.</span></span>  
  
 `ptkExportedType`  
 <span data-ttu-id="d67e4-109">[out]ポインター、`mdExportedType`エクスポートされる型を表すトークン。</span><span class="sxs-lookup"><span data-stu-id="d67e4-109">[out] A pointer to the `mdExportedType` token that represents the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d67e4-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="d67e4-110">Remarks</span></span>  
 <span data-ttu-id="d67e4-111">`FindExportedTypeByName`メソッドは、参照を解決するための共通言語ランタイムによって使用されている標準の規則を使用します。</span><span class="sxs-lookup"><span data-stu-id="d67e4-111">The `FindExportedTypeByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d67e4-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="d67e4-112">Requirements</span></span>  
 <span data-ttu-id="d67e4-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d67e4-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d67e4-114">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d67e4-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d67e4-115">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="d67e4-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d67e4-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d67e4-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d67e4-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="d67e4-117">See also</span></span>

- [<span data-ttu-id="d67e4-118">IMetaDataAssemblyImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d67e4-118">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="d67e4-119">ランタイムがアセンブリを検索する方法</span><span class="sxs-lookup"><span data-stu-id="d67e4-119">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
