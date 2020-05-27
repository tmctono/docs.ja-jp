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
ms.openlocfilehash: 220556ec130c7bff7c413405820c4fee0582b051
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008015"
---
# <a name="imetadataemitsetfieldprops-method"></a><span data-ttu-id="87736-102">IMetaDataEmit::SetFieldProps メソッド</span><span class="sxs-lookup"><span data-stu-id="87736-102">IMetaDataEmit::SetFieldProps Method</span></span>
<span data-ttu-id="87736-103">指定したフィールドトークンによって参照されるフィールドの既定値を設定または更新します。</span><span class="sxs-lookup"><span data-stu-id="87736-103">Sets or updates the default value for the field referenced by the specified field token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87736-104">構文</span><span class="sxs-lookup"><span data-stu-id="87736-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFieldProps (  
    [in]  mdFieldDef  fd,
    [in]  DWORD       dwFieldFlags,
    [in]  DWORD       dwCPlusTypeFlag,
    [in]  void const  *pValue,
    [in]  ULONG       cchValue
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="87736-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="87736-105">Parameters</span></span>  
 `fd`  
 <span data-ttu-id="87736-106">からターゲットフィールドのトークン。</span><span class="sxs-lookup"><span data-stu-id="87736-106">[in] The token for the target field.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="87736-107">からフィールド属性。</span><span class="sxs-lookup"><span data-stu-id="87736-107">[in] Field attributes.</span></span> <span data-ttu-id="87736-108">これは、値のビットマスクです `CorFieldAttr` 。</span><span class="sxs-lookup"><span data-stu-id="87736-108">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="87736-109">から`ELEMENT_TYPE_` *\** 定数値の。</span><span class="sxs-lookup"><span data-stu-id="87736-109">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="87736-110">これは `CorElementType` 値です。</span><span class="sxs-lookup"><span data-stu-id="87736-110">This is a `CorElementType` value.</span></span> <span data-ttu-id="87736-111">定数が定義されていない場合は、この値をに設定 `ELEMENT_TYPE_END` します。</span><span class="sxs-lookup"><span data-stu-id="87736-111">If a constant is not being defined, set this value to `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="87736-112">からフィールドの定数値。</span><span class="sxs-lookup"><span data-stu-id="87736-112">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="87736-113">からのサイズ (Unicode 文字) `pValue` 。</span><span class="sxs-lookup"><span data-stu-id="87736-113">[in] The size, in Unicode characters, of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87736-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="87736-114">Requirements</span></span>  
 <span data-ttu-id="87736-115">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87736-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87736-116">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="87736-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="87736-117">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="87736-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="87736-118">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87736-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87736-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="87736-119">See also</span></span>

- [<span data-ttu-id="87736-120">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="87736-120">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="87736-121">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="87736-121">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
