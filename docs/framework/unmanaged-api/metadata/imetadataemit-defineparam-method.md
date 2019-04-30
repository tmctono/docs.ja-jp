---
title: IMetaDataEmit::DefineParam メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineParam
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineParam
helpviewer_keywords:
- IMetaDataEmit::DefineParam method [.NET Framework metadata]
- DefineParam method [.NET Framework metadata]
ms.assetid: d86a3d14-4796-4909-9591-dfafe3de5ce4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 86711d107636505ab7aa23f0f72f70bd3e27635d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992655"
---
# <a name="imetadataemitdefineparam-method"></a><span data-ttu-id="32fef-102">IMetaDataEmit::DefineParam メソッド</span><span class="sxs-lookup"><span data-stu-id="32fef-102">IMetaDataEmit::DefineParam Method</span></span>
<span data-ttu-id="32fef-103">指定したトークンによって参照されるメソッドの指定したシグネチャを持つパラメーターの定義を作成し、そのパラメーターの定義のトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="32fef-103">Creates a parameter definition with the specified signature for the method referenced by the specified token, and gets a token for that parameter definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32fef-104">構文</span><span class="sxs-lookup"><span data-stu-id="32fef-104">Syntax</span></span>  
  
```  
HRESULT DefineParam (  
    [in]  mdMethodDef md,   
    [in]  ULONG       ulParamSeq,   
    [in]  LPCWSTR     szName,   
    [in]  DWORD       dwParamFlags,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,  
    [in]  ULONG       cchValue,   
    [out] mdParamDef  *ppd   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="32fef-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="32fef-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="32fef-106">[in]パラメーターが定義されているメソッドのトークン。</span><span class="sxs-lookup"><span data-stu-id="32fef-106">[in] The token for the method whose parameter is being defined.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="32fef-107">[in]パラメーターのシーケンス番号。</span><span class="sxs-lookup"><span data-stu-id="32fef-107">[in] The parameter sequence number.</span></span>  
  
 `szName`  
 <span data-ttu-id="32fef-108">[in]Unicode でパラメーターの名前。</span><span class="sxs-lookup"><span data-stu-id="32fef-108">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="32fef-109">[in]パラメーターのフラグ。</span><span class="sxs-lookup"><span data-stu-id="32fef-109">[in] Flags for the parameter.</span></span> <span data-ttu-id="32fef-110">これは、ビットマスクの`CorParamAttr`値。</span><span class="sxs-lookup"><span data-stu-id="32fef-110">This is a bitmask of `CorParamAttr` values.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="32fef-111">[in]`ELEMENT_TYPE_` *\** 定数の値。</span><span class="sxs-lookup"><span data-stu-id="32fef-111">[in] `ELEMENT_TYPE_`*\** for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="32fef-112">[in]パラメーターの定数値。</span><span class="sxs-lookup"><span data-stu-id="32fef-112">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="32fef-113">[in]Unicode 文字で、サイズの`pValue`します。</span><span class="sxs-lookup"><span data-stu-id="32fef-113">[in] The size, in Unicode characters, of `pValue`.</span></span>  
  
 `ppd`  
 <span data-ttu-id="32fef-114">[out]`mdParamDef`に割り当てられたトークン。</span><span class="sxs-lookup"><span data-stu-id="32fef-114">[out] The `mdParamDef` token assigned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="32fef-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="32fef-115">Remarks</span></span>  
 <span data-ttu-id="32fef-116">シーケンスの値で`ulParamSeq`パラメーターの 1 から始まります。</span><span class="sxs-lookup"><span data-stu-id="32fef-116">The sequence values in `ulParamSeq` begin with 1 for parameters.</span></span> <span data-ttu-id="32fef-117">戻り値は、シーケンス番号は 0 です。</span><span class="sxs-lookup"><span data-stu-id="32fef-117">A return value has a sequence number of 0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32fef-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="32fef-118">Requirements</span></span>  
 <span data-ttu-id="32fef-119">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="32fef-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32fef-120">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="32fef-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="32fef-121">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="32fef-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="32fef-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32fef-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32fef-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="32fef-123">See also</span></span>

- [<span data-ttu-id="32fef-124">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="32fef-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="32fef-125">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="32fef-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
