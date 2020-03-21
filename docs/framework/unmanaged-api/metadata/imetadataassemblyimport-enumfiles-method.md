---
title: IMetaDataAssemblyImport::EnumFiles メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumFiles
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumFiles
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumFiles method [.NET Framework metadata]
- EnumFiles method [.NET Framework metadata]
ms.assetid: f0d721e2-b946-426d-8e20-9124bd04e4cb
topic_type:
- apiref
ms.openlocfilehash: 70f76318f51047cb81262f744a6fbed5fe401692
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177817"
---
# <a name="imetadataassemblyimportenumfiles-method"></a><span data-ttu-id="fe7a5-102">IMetaDataAssemblyImport::EnumFiles メソッド</span><span class="sxs-lookup"><span data-stu-id="fe7a5-102">IMetaDataAssemblyImport::EnumFiles Method</span></span>
<span data-ttu-id="fe7a5-103">現在のアセンブリ マニフェストで参照されているファイルを列挙します。</span><span class="sxs-lookup"><span data-stu-id="fe7a5-103">Enumerates the files referenced in the current assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe7a5-104">構文</span><span class="sxs-lookup"><span data-stu-id="fe7a5-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumFiles (  
    [in, out] HCORENUM    *phEnum,
    [out] mdFile          rFiles[],
    [in]  ULONG           cMax,
    [out] ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe7a5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fe7a5-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="fe7a5-106">[イン、アウト]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="fe7a5-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="fe7a5-107">このメソッドの最初の呼び出しでは、null 値である必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe7a5-107">This must be a null value for the first call of this method.</span></span>  
  
 `rFiles`  
 <span data-ttu-id="fe7a5-108">[アウト]メタデータ トークンを格納するために`mdFile`使用される配列。</span><span class="sxs-lookup"><span data-stu-id="fe7a5-108">[out] The array used to store the `mdFile` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="fe7a5-109">[in]に配置できるトークン`mdFile`の最大数`rFiles`。</span><span class="sxs-lookup"><span data-stu-id="fe7a5-109">[in] The maximum number of `mdFile` tokens that can be placed in `rFiles`.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="fe7a5-110">[アウト]に実際に`mdFile`配置されたトークンの`rFiles`数。</span><span class="sxs-lookup"><span data-stu-id="fe7a5-110">[out] The number of `mdFile` tokens actually placed in `rFiles`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fe7a5-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="fe7a5-111">Return Value</span></span>  
  
|<span data-ttu-id="fe7a5-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fe7a5-112">HRESULT</span></span>|<span data-ttu-id="fe7a5-113">説明</span><span class="sxs-lookup"><span data-stu-id="fe7a5-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="fe7a5-114">`EnumFiles`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="fe7a5-114">`EnumFiles` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="fe7a5-115">列挙するトークンがありません。</span><span class="sxs-lookup"><span data-stu-id="fe7a5-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="fe7a5-116">この場合、`pcTokens`ゼロに設定されます。</span><span class="sxs-lookup"><span data-stu-id="fe7a5-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fe7a5-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="fe7a5-117">Requirements</span></span>  
 <span data-ttu-id="fe7a5-118">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe7a5-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe7a5-119">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="fe7a5-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fe7a5-120">**ライブラリ:** MsCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="fe7a5-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fe7a5-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe7a5-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe7a5-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="fe7a5-122">See also</span></span>

- [<span data-ttu-id="fe7a5-123">IMetaDataAssemblyImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fe7a5-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
