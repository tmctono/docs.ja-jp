---
title: IMetaDataEmit2::SetGenericParamProps メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SetGenericParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SetGenericParamProps
helpviewer_keywords:
- IMetaDataEmit2::SetGenericParamProps method [.NET Framework metadata]
- SetGenericParamProps method [.NET Framework metadata]
ms.assetid: cd93a48d-1fed-4706-bec6-a05dc3b64fbd
topic_type:
- apiref
ms.openlocfilehash: fd7f149e806727d849cdceb3ffbc5dc7392fcf1d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177404"
---
# <a name="imetadataemit2setgenericparamprops-method"></a><span data-ttu-id="5dda7-102">IMetaDataEmit2::SetGenericParamProps メソッド</span><span class="sxs-lookup"><span data-stu-id="5dda7-102">IMetaDataEmit2::SetGenericParamProps Method</span></span>
<span data-ttu-id="5dda7-103">指定したトークンによって参照されるジェネリック パラメーター定義のプロパティ値を設定します。</span><span class="sxs-lookup"><span data-stu-id="5dda7-103">Sets property values for the generic parameter definition referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5dda7-104">構文</span><span class="sxs-lookup"><span data-stu-id="5dda7-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGenericParamProps (  
    [in] mdGenericParam   gp,
    [in] DWORD            dwParamFlags,
    [in] LPCWSTR          szName,
    [in] DWORD            reserved,
    [in] mdToken          rtkConstraints[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5dda7-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5dda7-105">Parameters</span></span>  
 `gp`  
 <span data-ttu-id="5dda7-106">[in]値を設定するジェネリック パラメーター定義のトークン。</span><span class="sxs-lookup"><span data-stu-id="5dda7-106">[in] The token for the generic parameter definition for which to set values.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="5dda7-107">[in]ジェネリック パラメーターの型を記述する[CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md)列挙体の値。</span><span class="sxs-lookup"><span data-stu-id="5dda7-107">[in] A value of the [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeration that describes the type for the generic parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="5dda7-108">[in] オプション。</span><span class="sxs-lookup"><span data-stu-id="5dda7-108">[in] Optional.</span></span> <span data-ttu-id="5dda7-109">値を設定するパラメータの名前。</span><span class="sxs-lookup"><span data-stu-id="5dda7-109">The name of the parameter for which to set values.</span></span>  
  
 `reserved`  
 <span data-ttu-id="5dda7-110">[入力] 将来の機能拡張に備えて予約されています。</span><span class="sxs-lookup"><span data-stu-id="5dda7-110">[in] Reserved for future extensibility.</span></span>  
  
 `rtkConstraints`  
 <span data-ttu-id="5dda7-111">[in] オプション。</span><span class="sxs-lookup"><span data-stu-id="5dda7-111">[in] Optional.</span></span> <span data-ttu-id="5dda7-112">型制約のゼロで終わる配列。</span><span class="sxs-lookup"><span data-stu-id="5dda7-112">A zero-terminated array of type constraints.</span></span> <span data-ttu-id="5dda7-113">配列メンバーは`mdTypeDef`、 、`mdTypeRef`または`mdTypeSpec`メタデータ・トークンでなければなりません。</span><span class="sxs-lookup"><span data-stu-id="5dda7-113">Array members must be an `mdTypeDef`, `mdTypeRef`, or `mdTypeSpec` metadata token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5dda7-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="5dda7-114">Requirements</span></span>  
 <span data-ttu-id="5dda7-115">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5dda7-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5dda7-116">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="5dda7-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5dda7-117">**ライブラリ:** MsCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="5dda7-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5dda7-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5dda7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5dda7-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="5dda7-119">See also</span></span>

- [<span data-ttu-id="5dda7-120">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5dda7-120">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="5dda7-121">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5dda7-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
