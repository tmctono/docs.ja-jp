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
ms.openlocfilehash: 8feba8e67f3a90dd48fd957065a9c166c204b87c
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492735"
---
# <a name="imetadataemit2setgenericparamprops-method"></a><span data-ttu-id="a83b4-102">IMetaDataEmit2::SetGenericParamProps メソッド</span><span class="sxs-lookup"><span data-stu-id="a83b4-102">IMetaDataEmit2::SetGenericParamProps Method</span></span>
<span data-ttu-id="a83b4-103">指定したトークンによって参照されるジェネリックパラメーター定義のプロパティ値を設定します。</span><span class="sxs-lookup"><span data-stu-id="a83b4-103">Sets property values for the generic parameter definition referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a83b4-104">構文</span><span class="sxs-lookup"><span data-stu-id="a83b4-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGenericParamProps (  
    [in] mdGenericParam   gp,
    [in] DWORD            dwParamFlags,
    [in] LPCWSTR          szName,
    [in] DWORD            reserved,
    [in] mdToken          rtkConstraints[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a83b4-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a83b4-105">Parameters</span></span>  
 `gp`  
 <span data-ttu-id="a83b4-106">から値を設定するジェネリックパラメーター定義のトークン。</span><span class="sxs-lookup"><span data-stu-id="a83b4-106">[in] The token for the generic parameter definition for which to set values.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="a83b4-107">からジェネリックパラメーターの型を記述する[Corgenericparamattr](corgenericparamattr-enumeration.md)列挙体の値。</span><span class="sxs-lookup"><span data-stu-id="a83b4-107">[in] A value of the [CorGenericParamAttr](corgenericparamattr-enumeration.md) enumeration that describes the type for the generic parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="a83b4-108">[in] オプション。</span><span class="sxs-lookup"><span data-stu-id="a83b4-108">[in] Optional.</span></span> <span data-ttu-id="a83b4-109">値を設定するパラメーターの名前。</span><span class="sxs-lookup"><span data-stu-id="a83b4-109">The name of the parameter for which to set values.</span></span>  
  
 `reserved`  
 <span data-ttu-id="a83b4-110">[入力] 将来の機能拡張に備えて予約されています。</span><span class="sxs-lookup"><span data-stu-id="a83b4-110">[in] Reserved for future extensibility.</span></span>  
  
 `rtkConstraints`  
 <span data-ttu-id="a83b4-111">[in] オプション。</span><span class="sxs-lookup"><span data-stu-id="a83b4-111">[in] Optional.</span></span> <span data-ttu-id="a83b4-112">型制約の0から終わる配列。</span><span class="sxs-lookup"><span data-stu-id="a83b4-112">A zero-terminated array of type constraints.</span></span> <span data-ttu-id="a83b4-113">配列メンバーは `mdTypeDef` 、、 `mdTypeRef` 、またはメタデータトークンである必要があり `mdTypeSpec` ます。</span><span class="sxs-lookup"><span data-stu-id="a83b4-113">Array members must be an `mdTypeDef`, `mdTypeRef`, or `mdTypeSpec` metadata token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a83b4-114">要件</span><span class="sxs-lookup"><span data-stu-id="a83b4-114">Requirements</span></span>  
 <span data-ttu-id="a83b4-115">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a83b4-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a83b4-116">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="a83b4-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a83b4-117">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="a83b4-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a83b4-118">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a83b4-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a83b4-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="a83b4-119">See also</span></span>

- [<span data-ttu-id="a83b4-120">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a83b4-120">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="a83b4-121">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a83b4-121">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
