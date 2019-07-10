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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b32c402b20f9d7f0d370cfa6ec8376603efa8c3f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777992"
---
# <a name="imetadataassemblyimportenumfiles-method"></a><span data-ttu-id="bd844-102">IMetaDataAssemblyImport::EnumFiles メソッド</span><span class="sxs-lookup"><span data-stu-id="bd844-102">IMetaDataAssemblyImport::EnumFiles Method</span></span>
<span data-ttu-id="bd844-103">現在のアセンブリ マニフェストで参照されるファイルを列挙します。</span><span class="sxs-lookup"><span data-stu-id="bd844-103">Enumerates the files referenced in the current assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd844-104">構文</span><span class="sxs-lookup"><span data-stu-id="bd844-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumFiles (  
    [in, out] HCORENUM    *phEnum,   
    [out] mdFile          rFiles[],   
    [in]  ULONG           cMax,   
    [out] ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd844-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bd844-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="bd844-106">[入力、出力]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="bd844-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="bd844-107">これには、このメソッドの最初の呼び出しで null 値があります。</span><span class="sxs-lookup"><span data-stu-id="bd844-107">This must be a null value for the first call of this method.</span></span>  
  
 `rFiles`  
 <span data-ttu-id="bd844-108">[out]配列の格納に使用される、`mdFile`メタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="bd844-108">[out] The array used to store the `mdFile` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="bd844-109">[in]最大数`mdFile`トークン内に配置できる`rFiles`します。</span><span class="sxs-lookup"><span data-stu-id="bd844-109">[in] The maximum number of `mdFile` tokens that can be placed in `rFiles`.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="bd844-110">[out]数`mdFile`トークンが実際に配置`rFiles`します。</span><span class="sxs-lookup"><span data-stu-id="bd844-110">[out] The number of `mdFile` tokens actually placed in `rFiles`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bd844-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="bd844-111">Return Value</span></span>  
  
|<span data-ttu-id="bd844-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bd844-112">HRESULT</span></span>|<span data-ttu-id="bd844-113">説明</span><span class="sxs-lookup"><span data-stu-id="bd844-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="bd844-114">`EnumFiles` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="bd844-114">`EnumFiles` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="bd844-115">トークンを列挙することはありません。</span><span class="sxs-lookup"><span data-stu-id="bd844-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="bd844-116">この場合、 `pcTokens` 0 に設定されます。</span><span class="sxs-lookup"><span data-stu-id="bd844-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bd844-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="bd844-117">Requirements</span></span>  
 <span data-ttu-id="bd844-118">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd844-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd844-119">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bd844-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bd844-120">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="bd844-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bd844-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd844-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd844-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="bd844-122">See also</span></span>

- [<span data-ttu-id="bd844-123">IMetaDataAssemblyImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bd844-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
