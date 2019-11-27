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
ms.openlocfilehash: 5c81bc82e19bce658336e4860a61f2721e17423d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431692"
---
# <a name="imetadataemitdefineparam-method"></a><span data-ttu-id="6d231-102">IMetaDataEmit::DefineParam メソッド</span><span class="sxs-lookup"><span data-stu-id="6d231-102">IMetaDataEmit::DefineParam Method</span></span>
<span data-ttu-id="6d231-103">指定したトークンによって参照されるメソッドに対して、指定したシグネチャを持つパラメーター定義を作成し、そのパラメーター定義のトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="6d231-103">Creates a parameter definition with the specified signature for the method referenced by the specified token, and gets a token for that parameter definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d231-104">構文</span><span class="sxs-lookup"><span data-stu-id="6d231-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="6d231-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6d231-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="6d231-106">からパラメーターが定義されているメソッドのトークン。</span><span class="sxs-lookup"><span data-stu-id="6d231-106">[in] The token for the method whose parameter is being defined.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="6d231-107">からパラメーターのシーケンス番号。</span><span class="sxs-lookup"><span data-stu-id="6d231-107">[in] The parameter sequence number.</span></span>  
  
 `szName`  
 <span data-ttu-id="6d231-108">からUnicode でのパラメーターの名前。</span><span class="sxs-lookup"><span data-stu-id="6d231-108">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="6d231-109">からパラメーターのフラグ。</span><span class="sxs-lookup"><span data-stu-id="6d231-109">[in] Flags for the parameter.</span></span> <span data-ttu-id="6d231-110">これは `CorParamAttr` 値のビットマスクです。</span><span class="sxs-lookup"><span data-stu-id="6d231-110">This is a bitmask of `CorParamAttr` values.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="6d231-111">[in] 定数値の *\** を `ELEMENT_TYPE_`します。</span><span class="sxs-lookup"><span data-stu-id="6d231-111">[in] `ELEMENT_TYPE_`*\** for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="6d231-112">からパラメーターの定数値。</span><span class="sxs-lookup"><span data-stu-id="6d231-112">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="6d231-113">から`pValue`のサイズ (Unicode 文字)。</span><span class="sxs-lookup"><span data-stu-id="6d231-113">[in] The size, in Unicode characters, of `pValue`.</span></span>  
  
 `ppd`  
 <span data-ttu-id="6d231-114">入出力割り当てられた `mdParamDef` トークン。</span><span class="sxs-lookup"><span data-stu-id="6d231-114">[out] The `mdParamDef` token assigned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6d231-115">コメント</span><span class="sxs-lookup"><span data-stu-id="6d231-115">Remarks</span></span>  
 <span data-ttu-id="6d231-116">`ulParamSeq` のシーケンス値は、パラメーターに対して1から始まります。</span><span class="sxs-lookup"><span data-stu-id="6d231-116">The sequence values in `ulParamSeq` begin with 1 for parameters.</span></span> <span data-ttu-id="6d231-117">戻り値のシーケンス番号は0です。</span><span class="sxs-lookup"><span data-stu-id="6d231-117">A return value has a sequence number of 0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d231-118">要件</span><span class="sxs-lookup"><span data-stu-id="6d231-118">Requirements</span></span>  
 <span data-ttu-id="6d231-119">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d231-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d231-120">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="6d231-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6d231-121">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="6d231-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6d231-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d231-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d231-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="6d231-123">See also</span></span>

- [<span data-ttu-id="6d231-124">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6d231-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="6d231-125">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6d231-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
