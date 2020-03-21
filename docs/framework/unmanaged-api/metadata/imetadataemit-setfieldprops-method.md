---
title: IMetaDataEmit::SetFieldProps メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetFieldProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetFieldProps
helpviewer_keywords:
- IMetaDataEmit::SetFieldProps method [.NET Framework metadata]
- SetFieldProps method [.NET Framework metadata]
ms.assetid: 47132dda-fa92-4bd1-ae4b-24cd9a60665a
topic_type:
- apiref
ms.openlocfilehash: b921118f7c43edef3c07cbb34cbbd9119d36ce51
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177548"
---
# <a name="imetadataemitsetfieldprops-method"></a><span data-ttu-id="fd91e-102">IMetaDataEmit::SetFieldProps メソッド</span><span class="sxs-lookup"><span data-stu-id="fd91e-102">IMetaDataEmit::SetFieldProps Method</span></span>
<span data-ttu-id="fd91e-103">指定したフィールド トークンによって参照されるフィールドの既定値を設定または更新します。</span><span class="sxs-lookup"><span data-stu-id="fd91e-103">Sets or updates the default value for the field referenced by the specified field token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd91e-104">構文</span><span class="sxs-lookup"><span data-stu-id="fd91e-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFieldProps (  
    [in]  mdFieldDef  fd,
    [in]  DWORD       dwFieldFlags,
    [in]  DWORD       dwCPlusTypeFlag,
    [in]  void const  *pValue,
    [in]  ULONG       cchValue
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd91e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fd91e-105">Parameters</span></span>  
 `fd`  
 <span data-ttu-id="fd91e-106">[in]ターゲット フィールドのトークン。</span><span class="sxs-lookup"><span data-stu-id="fd91e-106">[in] The token for the target field.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="fd91e-107">[in]フィールド属性。</span><span class="sxs-lookup"><span data-stu-id="fd91e-107">[in] Field attributes.</span></span> <span data-ttu-id="fd91e-108">これは値の`CorFieldAttr`ビットマスクです。</span><span class="sxs-lookup"><span data-stu-id="fd91e-108">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="fd91e-109">[in]`ELEMENT_TYPE_`*\** 定数値の場合。</span><span class="sxs-lookup"><span data-stu-id="fd91e-109">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="fd91e-110">これは値です`CorElementType`。</span><span class="sxs-lookup"><span data-stu-id="fd91e-110">This is a `CorElementType` value.</span></span> <span data-ttu-id="fd91e-111">定数が定義されていない場合は、この値を に`ELEMENT_TYPE_END`設定します。</span><span class="sxs-lookup"><span data-stu-id="fd91e-111">If a constant is not being defined, set this value to `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="fd91e-112">[in]フィールドの定数値。</span><span class="sxs-lookup"><span data-stu-id="fd91e-112">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="fd91e-113">[in]のサイズ (Unicode 文字) `pValue`</span><span class="sxs-lookup"><span data-stu-id="fd91e-113">[in] The size, in Unicode characters, of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd91e-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="fd91e-114">Requirements</span></span>  
 <span data-ttu-id="fd91e-115">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd91e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd91e-116">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="fd91e-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fd91e-117">**ライブラリ:** MSCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="fd91e-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fd91e-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd91e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd91e-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="fd91e-119">See also</span></span>

- [<span data-ttu-id="fd91e-120">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fd91e-120">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="fd91e-121">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fd91e-121">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
