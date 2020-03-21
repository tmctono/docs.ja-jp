---
title: IMetaDataAssemblyImport::EnumManifestResources メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumManifestResources
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumManifestResources
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumManifestResources method [.NET Framework metadata]
- EnumManifestResources method [.NET Framework metadata]
ms.assetid: 9543b111-5705-40c9-935c-a3ffc7a581aa
topic_type:
- apiref
ms.openlocfilehash: 22141cf46a965c0624c076bd1d86d2624e5a09f3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176020"
---
# <a name="imetadataassemblyimportenummanifestresources-method"></a><span data-ttu-id="fec4e-102">IMetaDataAssemblyImport::EnumManifestResources メソッド</span><span class="sxs-lookup"><span data-stu-id="fec4e-102">IMetaDataAssemblyImport::EnumManifestResources Method</span></span>
<span data-ttu-id="fec4e-103">現在のアセンブリ マニフェストで参照されるリソースの列挙子へのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="fec4e-103">Gets a pointer to an enumerator for the resources referenced in the current assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fec4e-104">構文</span><span class="sxs-lookup"><span data-stu-id="fec4e-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumManifestResources (  
    [in, out] HCORENUM         *phEnum,
    [out] mdManifestResource   rManifestResources[],
    [in]  ULONG                cMax,
    [out] ULONG                *pcTokens  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="fec4e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fec4e-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="fec4e-106">[イン、アウト]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="fec4e-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="fec4e-107">メソッドが初めて呼び出されたとき`EnumManifestResources`は、この値は NULL 値である必要があります。</span><span class="sxs-lookup"><span data-stu-id="fec4e-107">This must be a null value when the `EnumManifestResources` method is called for the first time.</span></span>  
  
 `rManifestResources`  
 <span data-ttu-id="fec4e-108">[アウト]メタデータ トークンを格納するために`mdManifestResource`使用される配列。</span><span class="sxs-lookup"><span data-stu-id="fec4e-108">[out] The array used to store the `mdManifestResource` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="fec4e-109">[in]に配置できるトークン`mdManifestResource`の最大数`rManifestResources`。</span><span class="sxs-lookup"><span data-stu-id="fec4e-109">[in] The maximum number of `mdManifestResource` tokens that can be placed in `rManifestResources`.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="fec4e-110">[アウト]に実際に`mdManifestResource`配置されたトークンの`rManifestResources`数。</span><span class="sxs-lookup"><span data-stu-id="fec4e-110">[out] The number of `mdManifestResource` tokens actually placed in `rManifestResources`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fec4e-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="fec4e-111">Return Value</span></span>  
  
|<span data-ttu-id="fec4e-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fec4e-112">HRESULT</span></span>|<span data-ttu-id="fec4e-113">説明</span><span class="sxs-lookup"><span data-stu-id="fec4e-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="fec4e-114">`EnumManifestResources`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="fec4e-114">`EnumManifestResources` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="fec4e-115">列挙するトークンがありません。</span><span class="sxs-lookup"><span data-stu-id="fec4e-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="fec4e-116">この場合、`pcTokens`ゼロに設定されます。</span><span class="sxs-lookup"><span data-stu-id="fec4e-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fec4e-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="fec4e-117">Requirements</span></span>  
 <span data-ttu-id="fec4e-118">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fec4e-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fec4e-119">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="fec4e-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fec4e-120">**ライブラリ:** MsCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="fec4e-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fec4e-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fec4e-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fec4e-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="fec4e-122">See also</span></span>

- [<span data-ttu-id="fec4e-123">IMetaDataAssemblyImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fec4e-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
