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
ms.openlocfilehash: 7a93bbe0d7a9d9e6ff7505bbc215efa79176ad1f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440438"
---
# <a name="imetadataemit2setgenericparamprops-method"></a><span data-ttu-id="27a3f-102">IMetaDataEmit2::SetGenericParamProps メソッド</span><span class="sxs-lookup"><span data-stu-id="27a3f-102">IMetaDataEmit2::SetGenericParamProps Method</span></span>
<span data-ttu-id="27a3f-103">指定したトークンによって参照されるジェネリックパラメーター定義のプロパティ値を設定します。</span><span class="sxs-lookup"><span data-stu-id="27a3f-103">Sets property values for the generic parameter definition referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27a3f-104">構文</span><span class="sxs-lookup"><span data-stu-id="27a3f-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGenericParamProps (  
    [in] mdGenericParam   gp,   
    [in] DWORD            dwParamFlags,   
    [in] LPCWSTR          szName,   
    [in] DWORD            reserved,   
    [in] mdToken          rtkConstraints[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27a3f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="27a3f-105">Parameters</span></span>  
 `gp`  
 <span data-ttu-id="27a3f-106">から値を設定するジェネリックパラメーター定義のトークン。</span><span class="sxs-lookup"><span data-stu-id="27a3f-106">[in] The token for the generic parameter definition for which to set values.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="27a3f-107">からジェネリックパラメーターの型を記述する[Corgenericparamattr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md)列挙体の値。</span><span class="sxs-lookup"><span data-stu-id="27a3f-107">[in] A value of the [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeration that describes the type for the generic parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="27a3f-108">[in] オプション。</span><span class="sxs-lookup"><span data-stu-id="27a3f-108">[in] Optional.</span></span> <span data-ttu-id="27a3f-109">値を設定するパラメーターの名前。</span><span class="sxs-lookup"><span data-stu-id="27a3f-109">The name of the parameter for which to set values.</span></span>  
  
 `reserved`  
 <span data-ttu-id="27a3f-110">[入力] 将来の機能拡張に備えて予約されています。</span><span class="sxs-lookup"><span data-stu-id="27a3f-110">[in] Reserved for future extensibility.</span></span>  
  
 `rtkConstraints`  
 <span data-ttu-id="27a3f-111">[in] オプション。</span><span class="sxs-lookup"><span data-stu-id="27a3f-111">[in] Optional.</span></span> <span data-ttu-id="27a3f-112">型制約の0から終わる配列。</span><span class="sxs-lookup"><span data-stu-id="27a3f-112">A zero-terminated array of type constraints.</span></span> <span data-ttu-id="27a3f-113">配列メンバーは、`mdTypeDef`、`mdTypeRef`、または `mdTypeSpec` メタデータトークンである必要があります。</span><span class="sxs-lookup"><span data-stu-id="27a3f-113">Array members must be an `mdTypeDef`, `mdTypeRef`, or `mdTypeSpec` metadata token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27a3f-114">要件</span><span class="sxs-lookup"><span data-stu-id="27a3f-114">Requirements</span></span>  
 <span data-ttu-id="27a3f-115">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27a3f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27a3f-116">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="27a3f-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="27a3f-117">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="27a3f-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="27a3f-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27a3f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27a3f-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="27a3f-119">See also</span></span>

- [<span data-ttu-id="27a3f-120">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="27a3f-120">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="27a3f-121">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="27a3f-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
