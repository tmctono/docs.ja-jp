---
title: IMetaDataAssemblyImport::EnumExportedTypes メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumExportedTypes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumExportedTypes
helpviewer_keywords:
- EnumExportedTypes method [.NET Framework metadata]
- IMetaDataAssemblyImport::EnumExportedTypes method [.NET Framework metadata]
ms.assetid: e5912ed8-e4ce-438b-8ea3-d9e4c288d109
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 62c44d0c3bd2e931b1708abb48bc9c854431419f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751153"
---
# <a name="imetadataassemblyimportenumexportedtypes-method"></a><span data-ttu-id="0caeb-102">IMetaDataAssemblyImport::EnumExportedTypes メソッド</span><span class="sxs-lookup"><span data-stu-id="0caeb-102">IMetaDataAssemblyImport::EnumExportedTypes Method</span></span>
<span data-ttu-id="0caeb-103">現在のメタデータ スコープ内のアセンブリ マニフェストで参照されているエクスポートされた型を列挙します。</span><span class="sxs-lookup"><span data-stu-id="0caeb-103">Enumerates the exported types referenced in the assembly manifest in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0caeb-104">構文</span><span class="sxs-lookup"><span data-stu-id="0caeb-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumExportedTypes (  
    [in, out] HCORENUM     *phEnum,   
    [out] mdExportedType   rExportedTypes[],   
    [in]  ULONG            cMax,   
    [out] ULONG            *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0caeb-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0caeb-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="0caeb-106">[入力、出力]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="0caeb-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="0caeb-107">これを null には値と、`EnumExportedTypes`メソッドは、最初に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="0caeb-107">This must be a null value when the `EnumExportedTypes` method is called for the first time.</span></span>  
  
 `rExportedTypes`  
 <span data-ttu-id="0caeb-108">[out]列挙体`mdExportedType`メタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="0caeb-108">[out] The enumeration of `mdExportedType` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="0caeb-109">[in]最大数`mdExportedType`トークン内に配置できる、`rExportedTypes`配列。</span><span class="sxs-lookup"><span data-stu-id="0caeb-109">[in] The maximum number of `mdExportedType` tokens that can be placed in the `rExportedTypes` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="0caeb-110">[out]数`mdExportedType`トークンが実際に配置`rExportedTypes`します。</span><span class="sxs-lookup"><span data-stu-id="0caeb-110">[out] The number of `mdExportedType` tokens actually placed in `rExportedTypes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0caeb-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="0caeb-111">Return Value</span></span>  
  
|<span data-ttu-id="0caeb-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0caeb-112">HRESULT</span></span>|<span data-ttu-id="0caeb-113">説明</span><span class="sxs-lookup"><span data-stu-id="0caeb-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="0caeb-114">`EnumExportedTypes` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="0caeb-114">`EnumExportedTypes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="0caeb-115">トークンを列挙することはありません。</span><span class="sxs-lookup"><span data-stu-id="0caeb-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="0caeb-116">この場合、 `pcTokens` 0 に設定されます。</span><span class="sxs-lookup"><span data-stu-id="0caeb-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0caeb-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="0caeb-117">Requirements</span></span>  
 <span data-ttu-id="0caeb-118">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0caeb-118">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0caeb-119">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0caeb-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0caeb-120">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="0caeb-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0caeb-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0caeb-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0caeb-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="0caeb-122">See also</span></span>

- [<span data-ttu-id="0caeb-123">IMetaDataAssemblyImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0caeb-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
