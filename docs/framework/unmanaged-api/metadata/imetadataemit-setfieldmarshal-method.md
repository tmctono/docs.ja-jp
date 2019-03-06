---
title: IMetaDataEmit::SetFieldMarshal メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetFieldMarshal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetFieldMarshal
helpviewer_keywords:
- SetFieldMarshal method [.NET Framework metadata]
- IMetaDataEmit::SetFieldMarshal method [.NET Framework metadata]
ms.assetid: be232314-7f69-4855-bfab-63361bd22307
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9842108e9a26d7cca621c06b8ae1713e17c97ebe
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57476361"
---
# <a name="imetadataemitsetfieldmarshal-method"></a><span data-ttu-id="56a73-102">IMetaDataEmit::SetFieldMarshal メソッド</span><span class="sxs-lookup"><span data-stu-id="56a73-102">IMetaDataEmit::SetFieldMarshal Method</span></span>
<span data-ttu-id="56a73-103">指定したトークンによって参照されるフィールド、メソッドの戻り値、またはメソッドのパラメーターのマーシャ リング情報 PInvoke を設定します。</span><span class="sxs-lookup"><span data-stu-id="56a73-103">Sets the PInvoke marshaling information for the field, method return, or method parameter referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56a73-104">構文</span><span class="sxs-lookup"><span data-stu-id="56a73-104">Syntax</span></span>  
  
```  
HRESULT SetFieldMarshal (  
    [in]  mdToken          tk,   
    [in]  PCCOR_SIGNATURE  pvNativeType,   
    [in]  ULONG            cbNativeType   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="56a73-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="56a73-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="56a73-106">[in]ターゲット データ項目のトークンです。</span><span class="sxs-lookup"><span data-stu-id="56a73-106">[in] The token for target data item.</span></span> <span data-ttu-id="56a73-107">いずれかになります、`mdFieldDef`または`mdParamDef`トークンです。</span><span class="sxs-lookup"><span data-stu-id="56a73-107">This is either a `mdFieldDef` or a `mdParamDef` token.</span></span>  
  
 `pvNativeType`  
 <span data-ttu-id="56a73-108">[in]アンマネージ型のシグネチャ。</span><span class="sxs-lookup"><span data-stu-id="56a73-108">[in] The signature for unmanaged type.</span></span>  
  
 `cbNativeType`  
 <span data-ttu-id="56a73-109">[in]内のバイト数`pvNativeType`します。</span><span class="sxs-lookup"><span data-stu-id="56a73-109">[in] The count of bytes in `pvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56a73-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="56a73-110">Requirements</span></span>  
 <span data-ttu-id="56a73-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="56a73-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56a73-112">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="56a73-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="56a73-113">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="56a73-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="56a73-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56a73-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56a73-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="56a73-115">See also</span></span>
- [<span data-ttu-id="56a73-116">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="56a73-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="56a73-117">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="56a73-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
