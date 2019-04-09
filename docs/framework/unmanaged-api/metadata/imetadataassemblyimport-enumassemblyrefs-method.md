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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 91e253669b9f51e7c1d600ba11f13a9ce67fb58a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59072481"
---
# <a name="imetadataassemblyimportenumassemblyrefs-method"></a><span data-ttu-id="3a8b0-102">IMetaDataAssemblyImport::EnumAssemblyRefs メソッド</span><span class="sxs-lookup"><span data-stu-id="3a8b0-102">IMetaDataAssemblyImport::EnumAssemblyRefs Method</span></span>
<span data-ttu-id="3a8b0-103">列挙、`mdAssemblyRef`アセンブリ マニフェストで定義されているインスタンス。</span><span class="sxs-lookup"><span data-stu-id="3a8b0-103">Enumerates the `mdAssemblyRef` instances that are defined in the assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a8b0-104">構文</span><span class="sxs-lookup"><span data-stu-id="3a8b0-104">Syntax</span></span>  
  
```  
HRESULT EnumAssemblyRefs (  
    [in, out] HCORENUM        *phEnum,   
    [out]     mdAssemblyRef   rAssemblyRefs[],   
    [in]      ULONG           cMax,   
    [out]     ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a8b0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3a8b0-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="3a8b0-106">[入力、出力]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="3a8b0-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="3a8b0-107">これを null には値と、`EnumAssemblyRefs`メソッドは、最初に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="3a8b0-107">This must be a null value when the `EnumAssemblyRefs` method is called for the first time.</span></span>  
  
 `rAssemblyRefs`  
 <span data-ttu-id="3a8b0-108">[out]列挙体`mdAssemblyRef`メタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="3a8b0-108">[out] The enumeration of `mdAssemblyRef` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="3a8b0-109">[in]配置できるトークンの最大数、`rAssemblyRefs`配列。</span><span class="sxs-lookup"><span data-stu-id="3a8b0-109">[in] The maximum number of tokens that can be placed in the `rAssemblyRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="3a8b0-110">[out]トークンの数が実際に配置`rAssemblyRefs`します。</span><span class="sxs-lookup"><span data-stu-id="3a8b0-110">[out] The number of tokens actually placed in `rAssemblyRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3a8b0-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="3a8b0-111">Return Value</span></span>  
  
|<span data-ttu-id="3a8b0-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3a8b0-112">HRESULT</span></span>|<span data-ttu-id="3a8b0-113">説明</span><span class="sxs-lookup"><span data-stu-id="3a8b0-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumAssemblyRefs` <span data-ttu-id="3a8b0-114">正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="3a8b0-114">returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="3a8b0-115">トークンを列挙することはありません。</span><span class="sxs-lookup"><span data-stu-id="3a8b0-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="3a8b0-116">この場合、 `pcTokens` 0 に設定されます。</span><span class="sxs-lookup"><span data-stu-id="3a8b0-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3a8b0-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="3a8b0-117">Requirements</span></span>  
 <span data-ttu-id="3a8b0-118">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a8b0-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a8b0-119">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3a8b0-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3a8b0-120">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="3a8b0-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="3a8b0-121">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="3a8b0-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3a8b0-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="3a8b0-122">See also</span></span>

- [<span data-ttu-id="3a8b0-123">IMetaDataAssemblyImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3a8b0-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
