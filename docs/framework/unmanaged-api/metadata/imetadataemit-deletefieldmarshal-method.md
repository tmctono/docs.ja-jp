---
title: IMetaDataEmit::DeleteFieldMarshal メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DeleteFieldMarshal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DeleteFieldMarshal
helpviewer_keywords:
- IMetaDataEmit::DeleteFieldMarshal method [.NET Framework metadata]
- DeleteFieldMarshal method [.NET Framework metadata]
ms.assetid: 7c75aef9-c742-4b33-a14b-56ff94b0f725
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cf9cc16ba2702e814f27adb009a5e9b63acc97e3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57500195"
---
# <a name="imetadataemitdeletefieldmarshal-method"></a><span data-ttu-id="de54e-102">IMetaDataEmit::DeleteFieldMarshal メソッド</span><span class="sxs-lookup"><span data-stu-id="de54e-102">IMetaDataEmit::DeleteFieldMarshal Method</span></span>
<span data-ttu-id="de54e-103">指定したトークンによって参照されるオブジェクトのメタデータ シグネチャのマーシャ リング PInvoke を破棄します。</span><span class="sxs-lookup"><span data-stu-id="de54e-103">Destroys the PInvoke marshaling metadata signature for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de54e-104">構文</span><span class="sxs-lookup"><span data-stu-id="de54e-104">Syntax</span></span>  
  
```  
HRESULT DeleteFieldMarshal (  
    [in]  mdToken     tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="de54e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="de54e-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="de54e-106">[in]`mdFieldDef`または`mdParamDef`フィールドまたはマーシャ リングのメタデータ署名を削除するパラメーターを表すトークン。</span><span class="sxs-lookup"><span data-stu-id="de54e-106">[in] An `mdFieldDef` or `mdParamDef` token that represents the field or parameter for which to delete the marshaling metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de54e-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="de54e-107">Requirements</span></span>  
 <span data-ttu-id="de54e-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="de54e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de54e-109">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="de54e-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="de54e-110">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="de54e-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="de54e-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de54e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de54e-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="de54e-112">See also</span></span>
- [<span data-ttu-id="de54e-113">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="de54e-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="de54e-114">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="de54e-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
