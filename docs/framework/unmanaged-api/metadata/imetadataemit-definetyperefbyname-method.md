---
title: IMetaDataEmit::DefineTypeRefByName メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineTypeRefByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineTypeRefByName
helpviewer_keywords:
- DefineTypeRefByName method [.NET Framework metadata]
- IMetaDataEmit::DefineTypeRefByName method [.NET Framework metadata]
ms.assetid: c30a4ce3-2d3e-411a-98df-e62ac4a5dd50
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d93c55cec3d35fd4208a4a8a7c9b235dd10fb9ca
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59156170"
---
# <a name="imetadataemitdefinetyperefbyname-method"></a><span data-ttu-id="cadfb-102">IMetaDataEmit::DefineTypeRefByName メソッド</span><span class="sxs-lookup"><span data-stu-id="cadfb-102">IMetaDataEmit::DefineTypeRefByName Method</span></span>
<span data-ttu-id="cadfb-103">現在のスコープ外には、指定したスコープで定義されている型のメタデータ トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="cadfb-103">Gets a metadata token for a type that is defined in the specified scope, which is outside the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cadfb-104">構文</span><span class="sxs-lookup"><span data-stu-id="cadfb-104">Syntax</span></span>  
  
```  
HRESULT DefineTypeRefByName (   
    [in]  mdToken     tkResolutionScope,   
    [in]  LPCWSTR     szName,   
    [out] mdTypeRef   *ptr   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cadfb-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cadfb-105">Parameters</span></span>  
 `tkResolutionScope`  
 <span data-ttu-id="cadfb-106">[in]解決スコープを指定するトークンです。</span><span class="sxs-lookup"><span data-stu-id="cadfb-106">[in] The token specifying the resolution scope.</span></span> <span data-ttu-id="cadfb-107">次のトークン型は有効です。</span><span class="sxs-lookup"><span data-stu-id="cadfb-107">The following token types are valid:</span></span>  
  
-   `mdModuleRef`<span data-ttu-id="cadfb-108">、呼び出し元が定義されている同じアセンブリで型が定義されている場合。</span><span class="sxs-lookup"><span data-stu-id="cadfb-108">, if the type is defined in the same assembly in which the caller is defined.</span></span>  
  
-   `mdAssemblyRef`<span data-ttu-id="cadfb-109">、呼び出し元が定義されているもの以外のアセンブリで型が定義されている場合。</span><span class="sxs-lookup"><span data-stu-id="cadfb-109">, if the type is defined in an assembly other than the one in which the caller is defined.</span></span>  
  
-   `mdTypeRef`<span data-ttu-id="cadfb-110">、型が入れ子にされた型の場合。</span><span class="sxs-lookup"><span data-stu-id="cadfb-110">, if the type is a nested type.</span></span>  
  
-   `mdModule`<span data-ttu-id="cadfb-111">、、型が、呼び出し元が定義されている同じモジュールで定義されている場合。</span><span class="sxs-lookup"><span data-stu-id="cadfb-111">, if the type is defined in the same module in which the caller is defined.</span></span>  
  
-   <span data-ttu-id="cadfb-112">型がグローバルに定義されている場合は null です。</span><span class="sxs-lookup"><span data-stu-id="cadfb-112">Null, if the type is defined globally.</span></span>  
  
 `szName`  
 <span data-ttu-id="cadfb-113">[in]Unicode で対象の型の名前。</span><span class="sxs-lookup"><span data-stu-id="cadfb-113">[in] The name of the target type in Unicode.</span></span>  
  
 `ptr`  
 <span data-ttu-id="cadfb-114">[out]ポインター、`mdTypeRef`型に割り当てられているトークンです。</span><span class="sxs-lookup"><span data-stu-id="cadfb-114">[out] A pointer to the `mdTypeRef` token that is assigned to the type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cadfb-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="cadfb-115">Requirements</span></span>  
 <span data-ttu-id="cadfb-116">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cadfb-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cadfb-117">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="cadfb-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cadfb-118">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="cadfb-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="cadfb-119">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="cadfb-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cadfb-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="cadfb-120">See also</span></span>

- [<span data-ttu-id="cadfb-121">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cadfb-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="cadfb-122">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cadfb-122">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
