---
title: IMetaDataEmit::SetParamProps メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetParamProps
helpviewer_keywords:
- IMetaDataEmit::SetParamProps method [.NET Framework metadata]
- SetParamProps method [.NET Framework metadata]
ms.assetid: a95a3908-9f87-4084-937e-8e01ef03ad63
topic_type:
- apiref
ms.openlocfilehash: 13220dcfdd260688494d5aebc50f94abf8a82215
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177506"
---
# <a name="imetadataemitsetparamprops-method"></a><span data-ttu-id="da85c-102">IMetaDataEmit::SetParamProps メソッド</span><span class="sxs-lookup"><span data-stu-id="da85c-102">IMetaDataEmit::SetParamProps Method</span></span>
<span data-ttu-id="da85c-103">[IMetaDataEmit::DefineParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md)への以前の呼び出しによって定義されたメソッド パラメーターの機能を設定または変更します。</span><span class="sxs-lookup"><span data-stu-id="da85c-103">Sets or changes features of a method parameter that was defined by a prior call to [IMetaDataEmit::DefineParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da85c-104">構文</span><span class="sxs-lookup"><span data-stu-id="da85c-104">Syntax</span></span>  
  
```cpp  
HRESULT SetParamProps (
    [in]  mdParamDef  pd,
    [in]  LPCWSTR     szName,
    [in]  DWORD       dwParamFlags,
    [in]  DWORD       dwCPlusTypeFlag,
    [in]  void const  *pValue,
    [in]  ULONG       cchValue
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da85c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="da85c-105">Parameters</span></span>  
 `pd`  
 <span data-ttu-id="da85c-106">[in]ターゲット パラメーターのトークン。</span><span class="sxs-lookup"><span data-stu-id="da85c-106">[in] The token for the target parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="da85c-107">[in]ユニコードのパラメータの名前。</span><span class="sxs-lookup"><span data-stu-id="da85c-107">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="da85c-108">[in]パラメーターのフラグ。</span><span class="sxs-lookup"><span data-stu-id="da85c-108">[in] The flags for the parameter.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="da85c-109">[in]定数値のELEMENT_TYPE_\* です。</span><span class="sxs-lookup"><span data-stu-id="da85c-109">[in] The ELEMENT_TYPE_\* for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="da85c-110">[in]パラメーターの定数値。</span><span class="sxs-lookup"><span data-stu-id="da85c-110">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="da85c-111">[in]のサイズ (Unicode) 文字`pValue`</span><span class="sxs-lookup"><span data-stu-id="da85c-111">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da85c-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="da85c-112">Requirements</span></span>  
 <span data-ttu-id="da85c-113">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da85c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da85c-114">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="da85c-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="da85c-115">**ライブラリ:** MSCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="da85c-115">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="da85c-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da85c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da85c-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="da85c-117">See also</span></span>

- [<span data-ttu-id="da85c-118">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="da85c-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="da85c-119">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="da85c-119">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
