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
ms.openlocfilehash: 2807458549db02598ba05f2aa80fa6ea6fbc5a13
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177695"
---
# <a name="imetadataemitdefineparam-method"></a><span data-ttu-id="b4fc0-102">IMetaDataEmit::DefineParam メソッド</span><span class="sxs-lookup"><span data-stu-id="b4fc0-102">IMetaDataEmit::DefineParam Method</span></span>
<span data-ttu-id="b4fc0-103">指定したトークンによって参照されるメソッドの指定したシグネチャを持つパラメーター定義を作成し、そのパラメーター定義のトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="b4fc0-103">Creates a parameter definition with the specified signature for the method referenced by the specified token, and gets a token for that parameter definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4fc0-104">構文</span><span class="sxs-lookup"><span data-stu-id="b4fc0-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="b4fc0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b4fc0-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="b4fc0-106">[in]パラメーターが定義されているメソッドのトークン。</span><span class="sxs-lookup"><span data-stu-id="b4fc0-106">[in] The token for the method whose parameter is being defined.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="b4fc0-107">[in]パラメーターのシーケンス番号。</span><span class="sxs-lookup"><span data-stu-id="b4fc0-107">[in] The parameter sequence number.</span></span>  
  
 `szName`  
 <span data-ttu-id="b4fc0-108">[in]ユニコードのパラメータの名前。</span><span class="sxs-lookup"><span data-stu-id="b4fc0-108">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="b4fc0-109">[in]パラメーターのフラグ。</span><span class="sxs-lookup"><span data-stu-id="b4fc0-109">[in] Flags for the parameter.</span></span> <span data-ttu-id="b4fc0-110">これは値の`CorParamAttr`ビットマスクです。</span><span class="sxs-lookup"><span data-stu-id="b4fc0-110">This is a bitmask of `CorParamAttr` values.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="b4fc0-111">[in]`ELEMENT_TYPE_`を定数値に対して指定*\** します。</span><span class="sxs-lookup"><span data-stu-id="b4fc0-111">[in] `ELEMENT_TYPE_`*\** for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="b4fc0-112">[in]パラメーターの定数値。</span><span class="sxs-lookup"><span data-stu-id="b4fc0-112">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="b4fc0-113">[in]のサイズ (Unicode 文字) `pValue`</span><span class="sxs-lookup"><span data-stu-id="b4fc0-113">[in] The size, in Unicode characters, of `pValue`.</span></span>  
  
 `ppd`  
 <span data-ttu-id="b4fc0-114">[アウト]割`mdParamDef`り当てられたトークン。</span><span class="sxs-lookup"><span data-stu-id="b4fc0-114">[out] The `mdParamDef` token assigned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b4fc0-115">解説</span><span class="sxs-lookup"><span data-stu-id="b4fc0-115">Remarks</span></span>  
 <span data-ttu-id="b4fc0-116">シーケンス値は、`ulParamSeq`パラメーターの場合は 1 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b4fc0-116">The sequence values in `ulParamSeq` begin with 1 for parameters.</span></span> <span data-ttu-id="b4fc0-117">戻り値のシーケンス番号は 0 です。</span><span class="sxs-lookup"><span data-stu-id="b4fc0-117">A return value has a sequence number of 0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4fc0-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="b4fc0-118">Requirements</span></span>  
 <span data-ttu-id="b4fc0-119">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4fc0-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4fc0-120">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="b4fc0-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b4fc0-121">**ライブラリ:** MSCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="b4fc0-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b4fc0-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4fc0-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4fc0-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="b4fc0-123">See also</span></span>

- [<span data-ttu-id="b4fc0-124">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b4fc0-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="b4fc0-125">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b4fc0-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
