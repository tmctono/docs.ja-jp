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
ms.openlocfilehash: b710f966f519e2702607b7e186fff5986110d391
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007820"
---
# <a name="imetadataemitsetparamprops-method"></a><span data-ttu-id="2af72-102">IMetaDataEmit::SetParamProps メソッド</span><span class="sxs-lookup"><span data-stu-id="2af72-102">IMetaDataEmit::SetParamProps Method</span></span>
<span data-ttu-id="2af72-103">[IMetaDataEmit::D efineParam](imetadataemit-defineparam-method.md)の前の呼び出しで定義されたメソッドパラメーターの機能を設定または変更します。</span><span class="sxs-lookup"><span data-stu-id="2af72-103">Sets or changes features of a method parameter that was defined by a prior call to [IMetaDataEmit::DefineParam](imetadataemit-defineparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2af72-104">構文</span><span class="sxs-lookup"><span data-stu-id="2af72-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="2af72-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2af72-105">Parameters</span></span>  
 `pd`  
 <span data-ttu-id="2af72-106">から対象のパラメーターのトークン。</span><span class="sxs-lookup"><span data-stu-id="2af72-106">[in] The token for the target parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="2af72-107">からUnicode でのパラメーターの名前。</span><span class="sxs-lookup"><span data-stu-id="2af72-107">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="2af72-108">からパラメーターのフラグ。</span><span class="sxs-lookup"><span data-stu-id="2af72-108">[in] The flags for the parameter.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="2af72-109">から定数値の ELEMENT_TYPE_ \*。</span><span class="sxs-lookup"><span data-stu-id="2af72-109">[in] The ELEMENT_TYPE_\* for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="2af72-110">からパラメーターの定数値。</span><span class="sxs-lookup"><span data-stu-id="2af72-110">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="2af72-111">からの (Unicode) 文字のサイズ `pValue` 。</span><span class="sxs-lookup"><span data-stu-id="2af72-111">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2af72-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="2af72-112">Requirements</span></span>  
 <span data-ttu-id="2af72-113">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2af72-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2af72-114">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="2af72-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2af72-115">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="2af72-115">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2af72-116">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2af72-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2af72-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="2af72-117">See also</span></span>

- [<span data-ttu-id="2af72-118">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2af72-118">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="2af72-119">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2af72-119">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
