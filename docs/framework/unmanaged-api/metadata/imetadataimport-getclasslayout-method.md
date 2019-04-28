---
title: IMetaDataImport::GetClassLayout メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetClassLayout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetClassLayout
helpviewer_keywords:
- IMetaDataImport::GetClassLayout method [.NET Framework metadata]
- GetClassLayout method, IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 8f35414d-f40b-4b99-8768-9adb675c622a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 11748d3ad99c4050045cce3786eec5604c02ac0f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777833"
---
# <a name="imetadataimportgetclasslayout-method"></a><span data-ttu-id="b3499-102">IMetaDataImport::GetClassLayout メソッド</span><span class="sxs-lookup"><span data-stu-id="b3499-102">IMetaDataImport::GetClassLayout Method</span></span>
<span data-ttu-id="b3499-103">指定した TypeDef トークンによって参照されるクラスのレイアウト情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="b3499-103">Gets layout information for the class referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3499-104">構文</span><span class="sxs-lookup"><span data-stu-id="b3499-104">Syntax</span></span>  
  
```  
HRESULT GetClassLayout  (   
   [in]  mdTypeDef          td,   
   [out] DWORD              *pdwPackSize,  
   [out] COR_FIELD_OFFSET   rFieldOffset[],  
   [in]  ULONG              cMax,  
   [out] ULONG              *pcFieldOffset,  
   [out] ULONG              *pulClassSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b3499-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b3499-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="b3499-106">[in]返されるレイアウトを使用して、クラスの TypeDef トークンです。</span><span class="sxs-lookup"><span data-stu-id="b3499-106">[in] The TypeDef token for the class with the layout to return.</span></span>  
  
 `pdwPackSize`  
 <span data-ttu-id="b3499-107">[out]1、2、4、8、または 16 では、クラスのパック サイズを表す値の 1 つ。</span><span class="sxs-lookup"><span data-stu-id="b3499-107">[out] One of the values 1, 2, 4, 8, or 16, representing the pack size of the class.</span></span>  
  
 `rFieldOffset`  
 <span data-ttu-id="b3499-108">[out]配列の[COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md)値。</span><span class="sxs-lookup"><span data-stu-id="b3499-108">[out] An array of [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) values.</span></span>  
  
 `cMax`  
 <span data-ttu-id="b3499-109">[in] `rFieldOffset` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="b3499-109">[in] The maximum size of the `rFieldOffset` array.</span></span>  
  
 `pcFieldOffset`  
 <span data-ttu-id="b3499-110">[out]返される要素の数`rFieldOffset`します。</span><span class="sxs-lookup"><span data-stu-id="b3499-110">[out] The number of elements returned in `rFieldOffset`.</span></span>  
  
 `pulClassSize`  
 <span data-ttu-id="b3499-111">[out]によって表されるクラスのバイト サイズ`td`します。</span><span class="sxs-lookup"><span data-stu-id="b3499-111">[out] The size in bytes of the class represented by `td`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3499-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="b3499-112">Requirements</span></span>  
 <span data-ttu-id="b3499-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3499-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3499-114">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b3499-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b3499-115">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="b3499-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b3499-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3499-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3499-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="b3499-117">See also</span></span>

- [<span data-ttu-id="b3499-118">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b3499-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="b3499-119">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b3499-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
