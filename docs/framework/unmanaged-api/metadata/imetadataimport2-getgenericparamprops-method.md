---
title: IMetaDataImport2::GetGenericParamProps メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetGenericParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetGenericParamProps
helpviewer_keywords:
- IMetaDataImport2::GetGenericParamProps method [.NET Framework metadata]
- GetGenericParamProps method [.NET Framework metadata]
ms.assetid: dbb21e67-712b-49e7-a27c-a1e73ffd46c5
topic_type:
- apiref
ms.openlocfilehash: a8c5dd263401002deaee3d21f1e41b41a29faec2
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427300"
---
# <a name="imetadataimport2getgenericparamprops-method"></a><span data-ttu-id="d7e35-102">IMetaDataImport2::GetGenericParamProps メソッド</span><span class="sxs-lookup"><span data-stu-id="d7e35-102">IMetaDataImport2::GetGenericParamProps Method</span></span>
<span data-ttu-id="d7e35-103">指定したトークンによって表されるジェネリックパラメーターに関連付けられているメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="d7e35-103">Gets the metadata associated with the generic parameter represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7e35-104">構文</span><span class="sxs-lookup"><span data-stu-id="d7e35-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGenericParamProps (  
   [in]  mdGenericParam  gp,  
   [out] ULONG           *pulParamSeq,  
   [out] DWORD           *pdwParamFlags,  
   [out] mdToken         *ptOwner,  
   [out] DWORD           *reserved,  
   [out] LPWSTR          wzName,  
   [in]  ULONG           cchName,  
   [out] ULONG           *pchName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7e35-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d7e35-105">Parameters</span></span>  
 `gp`  
 <span data-ttu-id="d7e35-106">からメタデータを返す対象のジェネリックパラメーターを表すトークン。</span><span class="sxs-lookup"><span data-stu-id="d7e35-106">[in] The token that represents the generic parameter for which to return metadata.</span></span>  
  
 `pulParamSeq`  
 <span data-ttu-id="d7e35-107">入出力親コンストラクターまたはメソッド内の `Type` パラメーターの序数位置。</span><span class="sxs-lookup"><span data-stu-id="d7e35-107">[out] The ordinal position of the `Type` parameter in the parent constructor or method.</span></span>  
  
 `pdwParamFlags`  
 <span data-ttu-id="d7e35-108">入出力ジェネリックパラメーターの `Type` を記述する[Corgenericparamattr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md)列挙体の値。</span><span class="sxs-lookup"><span data-stu-id="d7e35-108">[out] A value of the [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeration that describes the `Type` for the generic parameter.</span></span>  
  
 `ptOwner`  
 <span data-ttu-id="d7e35-109">入出力パラメーターの所有者を表す TypeDef または MethodDef トークン。</span><span class="sxs-lookup"><span data-stu-id="d7e35-109">[out] A TypeDef or MethodDef token that represents the owner of the parameter.</span></span>  
  
 `reserved`  
 <span data-ttu-id="d7e35-110">入出力将来の拡張のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="d7e35-110">[out] Reserved for future extensibility.</span></span>  
  
 `wzName`  
 <span data-ttu-id="d7e35-111">入出力ジェネリックパラメーターの名前。</span><span class="sxs-lookup"><span data-stu-id="d7e35-111">[out] The name of the generic parameter.</span></span>  
  
 `cchName`  
 <span data-ttu-id="d7e35-112">から`wzName` バッファーのサイズ。</span><span class="sxs-lookup"><span data-stu-id="d7e35-112">[in] The size of the `wzName` buffer.</span></span>  
  
 `pchName`  
 <span data-ttu-id="d7e35-113">入出力名前の返されたサイズ (ワイド文字単位)。</span><span class="sxs-lookup"><span data-stu-id="d7e35-113">[out] The returned size of the name, in wide characters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7e35-114">要件</span><span class="sxs-lookup"><span data-stu-id="d7e35-114">Requirements</span></span>  
 <span data-ttu-id="d7e35-115">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7e35-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7e35-116">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="d7e35-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d7e35-117">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="d7e35-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d7e35-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7e35-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7e35-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="d7e35-119">See also</span></span>

- [<span data-ttu-id="d7e35-120">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d7e35-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="d7e35-121">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d7e35-121">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
