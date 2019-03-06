---
title: IMetaDataImport::GetParamProps メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetParamProps
helpviewer_keywords:
- IMetaDataImport::GetParamProps method [.NET Framework metadata]
- GetParamProps method [.NET Framework metadata]
ms.assetid: 4d5e5f00-bcab-4f41-b191-176511a186a7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ed9bae4fde96f0878e40ed73b81cc8776571ada5
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468059"
---
# <a name="imetadataimportgetparamprops-method"></a><span data-ttu-id="53dc9-102">IMetaDataImport::GetParamProps メソッド</span><span class="sxs-lookup"><span data-stu-id="53dc9-102">IMetaDataImport::GetParamProps Method</span></span>
<span data-ttu-id="53dc9-103">指定した ParamDef トークンによって参照されるパラメーターのメタデータ値を取得します。</span><span class="sxs-lookup"><span data-stu-id="53dc9-103">Gets metadata values for the parameter referenced by the specified ParamDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53dc9-104">構文</span><span class="sxs-lookup"><span data-stu-id="53dc9-104">Syntax</span></span>  
  
```  
HRESULT GetParamProps (  
   [in]  mdParamDef      tk,  
   [out] mdMethodDef     *pmd,  
   [out] ULONG           *pulSequence,  
   [out] LPWSTR          szName,  
   [in]  ULONG           cchName,  
   [out] ULONG           *pchName,  
   [out] DWORD           *pdwAttr,  
   [out] DWORD           *pdwCPlusTypeFlag,  
   [out] UVCP_CONSTANT   *ppValue,  
   [out] ULONG           *pcchValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="53dc9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="53dc9-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="53dc9-106">[in]メタデータを返すパラメーターを表す ParamDef トークンです。</span><span class="sxs-lookup"><span data-stu-id="53dc9-106">[in] A ParamDef token that represents the parameter to return metadata for.</span></span>  
  
 `pmd`  
 <span data-ttu-id="53dc9-107">[out]パラメーターを受け取るメソッドを表す MethodDef トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="53dc9-107">[out] A pointer to a MethodDef token representing the method that takes the parameter.</span></span>  
  
 `pulSequence`  
 <span data-ttu-id="53dc9-108">[out]メソッドの引数リストで、パラメーターの序数の位置。</span><span class="sxs-lookup"><span data-stu-id="53dc9-108">[out] The ordinal position of the parameter in the method argument list.</span></span>  
  
 `szName`  
 <span data-ttu-id="53dc9-109">[out]パラメーターの名前を保持するバッファー。</span><span class="sxs-lookup"><span data-stu-id="53dc9-109">[out] A buffer to hold the name of the parameter.</span></span>  
  
 `cchName`  
 <span data-ttu-id="53dc9-110">[in]要求されたサイズのワイド文字単位`szName`します。</span><span class="sxs-lookup"><span data-stu-id="53dc9-110">[in] The requested size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="53dc9-111">[out]ワイド文字で返されるサイズ`szName`します。</span><span class="sxs-lookup"><span data-stu-id="53dc9-111">[out] The returned size in wide characters of `szName`.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="53dc9-112">[out]パラメーターに関連付けられているすべての属性フラグへのポインター。</span><span class="sxs-lookup"><span data-stu-id="53dc9-112">[out] A pointer to any attribute flags associated with the parameter.</span></span> <span data-ttu-id="53dc9-113">これは、ビットマスクの`CorParamAttr`値。</span><span class="sxs-lookup"><span data-stu-id="53dc9-113">This is a bitmask of `CorParamAttr` values.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="53dc9-114">[out]パラメーターを指定するフラグへのポインター、<xref:System.ValueType>します。</span><span class="sxs-lookup"><span data-stu-id="53dc9-114">[out] A pointer to a flag specifying that the parameter is a <xref:System.ValueType>.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="53dc9-115">[out]パラメーターによって返される定数文字列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="53dc9-115">[out] A pointer to a constant string returned by the parameter.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="53dc9-116">[out]サイズ`ppValue`ワイド文字、または場合は 0 で`ppValue`文字列を保持しません。</span><span class="sxs-lookup"><span data-stu-id="53dc9-116">[out] The size of `ppValue` in wide characters, or zero if `ppValue` does not hold a string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="53dc9-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="53dc9-117">Remarks</span></span>

<span data-ttu-id="53dc9-118">シーケンスの値で`pulSequence`パラメーターの 1 から始まります。</span><span class="sxs-lookup"><span data-stu-id="53dc9-118">The sequence values in `pulSequence` begin with 1 for parameters.</span></span> <span data-ttu-id="53dc9-119">戻り値は、シーケンス番号は 0 です。</span><span class="sxs-lookup"><span data-stu-id="53dc9-119">A return value has a sequence number of 0.</span></span>

## <a name="requirements"></a><span data-ttu-id="53dc9-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="53dc9-120">Requirements</span></span>  
 <span data-ttu-id="53dc9-121">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="53dc9-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53dc9-122">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="53dc9-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="53dc9-123">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="53dc9-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="53dc9-124">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53dc9-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53dc9-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="53dc9-125">See also</span></span>
- [<span data-ttu-id="53dc9-126">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="53dc9-126">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="53dc9-127">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="53dc9-127">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
