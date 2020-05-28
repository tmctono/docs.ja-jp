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
ms.openlocfilehash: ac6de9a16fad6ba9d14f3960ddd28c42c111f254
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009393"
---
# <a name="imetadataassemblyimportfindexportedtypebyname-method"></a><span data-ttu-id="984d0-102">IMetaDataAssemblyImport::FindExportedTypeByName メソッド</span><span class="sxs-lookup"><span data-stu-id="984d0-102">IMetaDataAssemblyImport::FindExportedTypeByName Method</span></span>
<span data-ttu-id="984d0-103">名前と外側の型を指定して、エクスポートされた型へのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="984d0-103">Gets a pointer to an exported type, given its name and enclosing type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="984d0-104">構文</span><span class="sxs-lookup"><span data-stu-id="984d0-104">Syntax</span></span>  
  
```cpp  
HRESULT FindExportedTypeByName (  
    [in]  LPCWSTR           szName,
    [in]  mdToken           mdtExportedType,
    [out] mdExportedType    *ptkExportedType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="984d0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="984d0-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="984d0-106">からエクスポートされた型の名前。</span><span class="sxs-lookup"><span data-stu-id="984d0-106">[in] The name of the exported type.</span></span>  
  
 `mdtExportedType`  
 <span data-ttu-id="984d0-107">からエクスポートする型の外側のクラスのメタデータトークン。</span><span class="sxs-lookup"><span data-stu-id="984d0-107">[in] The metadata token for the enclosing class of the exported type.</span></span> <span data-ttu-id="984d0-108">要求されたエクスポート型が入れ子にされた型では `mdExportedTypeNil` ない場合、この値はです。</span><span class="sxs-lookup"><span data-stu-id="984d0-108">This value is `mdExportedTypeNil` if the requested exported type is not a nested type.</span></span>  
  
 `ptkExportedType`  
 <span data-ttu-id="984d0-109">入出力エクスポートされた `mdExportedType` 型を表すトークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="984d0-109">[out] A pointer to the `mdExportedType` token that represents the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="984d0-110">コメント</span><span class="sxs-lookup"><span data-stu-id="984d0-110">Remarks</span></span>  
 <span data-ttu-id="984d0-111">メソッドは、 `FindExportedTypeByName` 参照を解決するために共通言語ランタイムによって採用されている標準の規則を使用します。</span><span class="sxs-lookup"><span data-stu-id="984d0-111">The `FindExportedTypeByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="984d0-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="984d0-112">Requirements</span></span>  
 <span data-ttu-id="984d0-113">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="984d0-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="984d0-114">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="984d0-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="984d0-115">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="984d0-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="984d0-116">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="984d0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="984d0-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="984d0-117">See also</span></span>

- [<span data-ttu-id="984d0-118">IMetaDataAssemblyImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="984d0-118">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
- [<span data-ttu-id="984d0-119">ランタイムがアセンブリを検索する方法</span><span class="sxs-lookup"><span data-stu-id="984d0-119">How the Runtime Locates Assemblies</span></span>](../../deployment/how-the-runtime-locates-assemblies.md)
