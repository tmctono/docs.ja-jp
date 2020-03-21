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
ms.openlocfilehash: f00fe5bce2f808265add228406dfaa2ccc267545
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176007"
---
# <a name="imetadataassemblyimportenumexportedtypes-method"></a><span data-ttu-id="9e6ee-102">IMetaDataAssemblyImport::EnumExportedTypes メソッド</span><span class="sxs-lookup"><span data-stu-id="9e6ee-102">IMetaDataAssemblyImport::EnumExportedTypes Method</span></span>
<span data-ttu-id="9e6ee-103">現在のメタデータ スコープ内のアセンブリ マニフェストで参照されるエクスポートされた型を列挙します。</span><span class="sxs-lookup"><span data-stu-id="9e6ee-103">Enumerates the exported types referenced in the assembly manifest in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e6ee-104">構文</span><span class="sxs-lookup"><span data-stu-id="9e6ee-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumExportedTypes (  
    [in, out] HCORENUM     *phEnum,
    [out] mdExportedType   rExportedTypes[],
    [in]  ULONG            cMax,
    [out] ULONG            *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e6ee-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9e6ee-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="9e6ee-106">[イン、アウト]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="9e6ee-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="9e6ee-107">メソッドが初めて呼び出されたとき`EnumExportedTypes`は、この値は NULL 値である必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e6ee-107">This must be a null value when the `EnumExportedTypes` method is called for the first time.</span></span>  
  
 `rExportedTypes`  
 <span data-ttu-id="9e6ee-108">[アウト]メタデータ トークン`mdExportedType`の列挙体。</span><span class="sxs-lookup"><span data-stu-id="9e6ee-108">[out] The enumeration of `mdExportedType` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="9e6ee-109">[in]配列に配置できる`mdExportedType`トークンの最大数。 `rExportedTypes`</span><span class="sxs-lookup"><span data-stu-id="9e6ee-109">[in] The maximum number of `mdExportedType` tokens that can be placed in the `rExportedTypes` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="9e6ee-110">[アウト]に実際に`mdExportedType`配置されたトークンの`rExportedTypes`数。</span><span class="sxs-lookup"><span data-stu-id="9e6ee-110">[out] The number of `mdExportedType` tokens actually placed in `rExportedTypes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9e6ee-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="9e6ee-111">Return Value</span></span>  
  
|<span data-ttu-id="9e6ee-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9e6ee-112">HRESULT</span></span>|<span data-ttu-id="9e6ee-113">説明</span><span class="sxs-lookup"><span data-stu-id="9e6ee-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="9e6ee-114">`EnumExportedTypes`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="9e6ee-114">`EnumExportedTypes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="9e6ee-115">列挙するトークンがありません。</span><span class="sxs-lookup"><span data-stu-id="9e6ee-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="9e6ee-116">この場合、`pcTokens`ゼロに設定されます。</span><span class="sxs-lookup"><span data-stu-id="9e6ee-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9e6ee-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="9e6ee-117">Requirements</span></span>  
 <span data-ttu-id="9e6ee-118">**プラットフォーム:**[「システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e6ee-118">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e6ee-119">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="9e6ee-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9e6ee-120">**ライブラリ:** MsCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="9e6ee-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9e6ee-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e6ee-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e6ee-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="9e6ee-122">See also</span></span>

- [<span data-ttu-id="9e6ee-123">IMetaDataAssemblyImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9e6ee-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
