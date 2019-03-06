---
title: IMetaDataImport::GetMethodSemantics メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMethodSemantics
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMethodSemantics
helpviewer_keywords:
- GetMethodSemantics method [.NET Framework metadata]
- IMetaDataImport::GetMethodSemantics method [.NET Framework metadata]
ms.assetid: 5e018eaa-d60e-4a0b-a2c5-8c36bd09d905
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 35b99240a99341ddf78ab43c444b503702af66c9
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479169"
---
# <a name="imetadataimportgetmethodsemantics-method"></a><span data-ttu-id="74143-102">IMetaDataImport::GetMethodSemantics メソッド</span><span class="sxs-lookup"><span data-stu-id="74143-102">IMetaDataImport::GetMethodSemantics Method</span></span>
<span data-ttu-id="74143-103">指定した MethodDef トークンとペアになっているプロパティによって参照されるメソッドと指定した EventProp によって参照されるイベント間のリレーションシップを示すフラグのトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="74143-103">Gets flags indicating the relationship between the method referenced by the specified MethodDef token and the paired property and event referenced by the specified EventProp token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74143-104">構文</span><span class="sxs-lookup"><span data-stu-id="74143-104">Syntax</span></span>  
  
```  
HRESULT GetMethodSemantics (  
   [in]  mdMethodDef   mb,  
   [in]  mdToken       tkEventProp,  
   [out] DWORD         *pdwSemanticsFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="74143-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="74143-105">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="74143-106">[in]セマンティックのロール情報を取得するメソッドを表す MethodDef トークンです。</span><span class="sxs-lookup"><span data-stu-id="74143-106">[in] A MethodDef token representing the method to get the semantic role information for.</span></span>  
  
 `tkEventProp`  
 <span data-ttu-id="74143-107">[in]ペアになっているプロパティとメソッドの役割を取得する対象のイベントを表すトークンです。</span><span class="sxs-lookup"><span data-stu-id="74143-107">[in] A token representing the paired property and event for which to get the method's role.</span></span>  
  
 `pdwSemanticsFlags`  
 <span data-ttu-id="74143-108">[out]関連付けられているセマンティクス フラグへのポインター。</span><span class="sxs-lookup"><span data-stu-id="74143-108">[out] A pointer to the associated semantics flags.</span></span> <span data-ttu-id="74143-109">この値はビットマスクから、 [CorMethodSemanticsAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodsemanticsattr-enumeration.md)列挙体。</span><span class="sxs-lookup"><span data-stu-id="74143-109">This value is a bitmask from the [CorMethodSemanticsAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodsemanticsattr-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="74143-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="74143-110">Remarks</span></span>  
 <span data-ttu-id="74143-111">[Imetadataemit::defineproperty](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md)メソッドは、メソッドのセマンティクスのフラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="74143-111">The [IMetaDataEmit::DefineProperty](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md) method sets a method's semantics flags.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74143-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="74143-112">Requirements</span></span>  
 <span data-ttu-id="74143-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="74143-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74143-114">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="74143-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="74143-115">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="74143-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="74143-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74143-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74143-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="74143-117">See also</span></span>
- [<span data-ttu-id="74143-118">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="74143-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="74143-119">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="74143-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
