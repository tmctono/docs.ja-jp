---
title: IMetaDataAssemblyImport::EnumAssemblyRefs メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumAssemblyRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumAssemblyRefs
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumAssemblyRefs method [.NET Framework metadata]
- EnumAssemblyRefs method [.NET Framework metadata]
ms.assetid: 8844d0dd-730e-4592-8a7b-c1462d312c70
topic_type:
- apiref
ms.openlocfilehash: 6a4489d094974eb872b39824ceb185b0cbe48625
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177826"
---
# <a name="imetadataassemblyimportenumassemblyrefs-method"></a><span data-ttu-id="af00f-102">IMetaDataAssemblyImport::EnumAssemblyRefs メソッド</span><span class="sxs-lookup"><span data-stu-id="af00f-102">IMetaDataAssemblyImport::EnumAssemblyRefs Method</span></span>
<span data-ttu-id="af00f-103">アセンブリ マニフェスト`mdAssemblyRef`で定義されているインスタンスを列挙します。</span><span class="sxs-lookup"><span data-stu-id="af00f-103">Enumerates the `mdAssemblyRef` instances that are defined in the assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af00f-104">構文</span><span class="sxs-lookup"><span data-stu-id="af00f-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumAssemblyRefs (  
    [in, out] HCORENUM        *phEnum,
    [out]     mdAssemblyRef   rAssemblyRefs[],
    [in]      ULONG           cMax,
    [out]     ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="af00f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="af00f-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="af00f-106">[イン、アウト]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="af00f-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="af00f-107">メソッドが初めて呼び出されたとき`EnumAssemblyRefs`は、この値は NULL 値である必要があります。</span><span class="sxs-lookup"><span data-stu-id="af00f-107">This must be a null value when the `EnumAssemblyRefs` method is called for the first time.</span></span>  
  
 `rAssemblyRefs`  
 <span data-ttu-id="af00f-108">[アウト]メタデータ トークン`mdAssemblyRef`の列挙体。</span><span class="sxs-lookup"><span data-stu-id="af00f-108">[out] The enumeration of `mdAssemblyRef` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="af00f-109">[in]`rAssemblyRefs`配列に配置できるトークンの最大数。</span><span class="sxs-lookup"><span data-stu-id="af00f-109">[in] The maximum number of tokens that can be placed in the `rAssemblyRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="af00f-110">[アウト]に実際に配置されたトークンの`rAssemblyRefs`数。</span><span class="sxs-lookup"><span data-stu-id="af00f-110">[out] The number of tokens actually placed in `rAssemblyRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="af00f-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="af00f-111">Return Value</span></span>  
  
|<span data-ttu-id="af00f-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="af00f-112">HRESULT</span></span>|<span data-ttu-id="af00f-113">説明</span><span class="sxs-lookup"><span data-stu-id="af00f-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="af00f-114">`EnumAssemblyRefs`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="af00f-114">`EnumAssemblyRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="af00f-115">列挙するトークンがありません。</span><span class="sxs-lookup"><span data-stu-id="af00f-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="af00f-116">この場合、`pcTokens`ゼロに設定されます。</span><span class="sxs-lookup"><span data-stu-id="af00f-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="af00f-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="af00f-117">Requirements</span></span>  
 <span data-ttu-id="af00f-118">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af00f-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af00f-119">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="af00f-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="af00f-120">**ライブラリ:** MsCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="af00f-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="af00f-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af00f-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af00f-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="af00f-122">See also</span></span>

- [<span data-ttu-id="af00f-123">IMetaDataAssemblyImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="af00f-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
