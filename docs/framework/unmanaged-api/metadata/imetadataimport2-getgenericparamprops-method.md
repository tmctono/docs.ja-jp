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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 55a765fe3942cbf71a8460187e829dc7f3ca877e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049857"
---
# <a name="imetadataimport2getgenericparamprops-method"></a><span data-ttu-id="7cfcd-102">IMetaDataImport2::GetGenericParamProps メソッド</span><span class="sxs-lookup"><span data-stu-id="7cfcd-102">IMetaDataImport2::GetGenericParamProps Method</span></span>
<span data-ttu-id="7cfcd-103">指定したトークンによって表されるジェネリック パラメーターに関連付けられているメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="7cfcd-103">Gets the metadata associated with the generic parameter represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cfcd-104">構文</span><span class="sxs-lookup"><span data-stu-id="7cfcd-104">Syntax</span></span>  
  
```  
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
  
## <a name="parameters"></a><span data-ttu-id="7cfcd-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7cfcd-105">Parameters</span></span>  
 `gp`  
 <span data-ttu-id="7cfcd-106">[in]メタデータを返す対象のジェネリック パラメーターを表すトークン。</span><span class="sxs-lookup"><span data-stu-id="7cfcd-106">[in] The token that represents the generic parameter for which to return metadata.</span></span>  
  
 `pulParamSeq`  
 <span data-ttu-id="7cfcd-107">[out]位置を表す序数、`Type`親コンス トラクターまたはメソッド パラメーター。</span><span class="sxs-lookup"><span data-stu-id="7cfcd-107">[out] The ordinal position of the `Type` parameter in the parent constructor or method.</span></span>  
  
 `pdwParamFlags`  
 <span data-ttu-id="7cfcd-108">[out]値、 [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md)を表す列挙体、`Type`のジェネリック パラメーター。</span><span class="sxs-lookup"><span data-stu-id="7cfcd-108">[out] A value of the [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeration that describes the `Type` for the generic parameter.</span></span>  
  
 `ptOwner`  
 <span data-ttu-id="7cfcd-109">[out]パラメーターの所有者を表す TypeDef または MethodDef トークンです。</span><span class="sxs-lookup"><span data-stu-id="7cfcd-109">[out] A TypeDef or MethodDef token that represents the owner of the parameter.</span></span>  
  
 `reserved`  
 <span data-ttu-id="7cfcd-110">[out]将来の機能拡張予約されています。</span><span class="sxs-lookup"><span data-stu-id="7cfcd-110">[out] Reserved for future extensibility.</span></span>  
  
 `wzName`  
 <span data-ttu-id="7cfcd-111">[out]ジェネリック パラメーターの名前。</span><span class="sxs-lookup"><span data-stu-id="7cfcd-111">[out] The name of the generic parameter.</span></span>  
  
 `cchName`  
 <span data-ttu-id="7cfcd-112">[in]サイズ、`wzName`バッファー。</span><span class="sxs-lookup"><span data-stu-id="7cfcd-112">[in] The size of the `wzName` buffer.</span></span>  
  
 `pchName`  
 <span data-ttu-id="7cfcd-113">[out]ワイド文字で、名前の返されたサイズ。</span><span class="sxs-lookup"><span data-stu-id="7cfcd-113">[out] The returned size of the name, in wide characters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7cfcd-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="7cfcd-114">Requirements</span></span>  
 <span data-ttu-id="7cfcd-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7cfcd-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7cfcd-116">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7cfcd-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7cfcd-117">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="7cfcd-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7cfcd-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7cfcd-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cfcd-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="7cfcd-119">See also</span></span>

- [<span data-ttu-id="7cfcd-120">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7cfcd-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="7cfcd-121">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7cfcd-121">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
