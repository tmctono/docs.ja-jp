---
title: IMetaDataEmit::DefineCustomAttribute メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineCustomAttribute
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineCustomAttribute
helpviewer_keywords:
- DefineCustomAttribute method [.NET Framework metadata]
- IMetaDataEmit::DefineCustomAttribute method [.NET Framework metadata]
ms.assetid: 7dd14854-b756-4401-b167-88ca576dc8f0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 52190583338f1c1ee9183a98d5f4a6cd7236342d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992551"
---
# <a name="imetadataemitdefinecustomattribute-method"></a><span data-ttu-id="7c041-102">IMetaDataEmit::DefineCustomAttribute メソッド</span><span class="sxs-lookup"><span data-stu-id="7c041-102">IMetaDataEmit::DefineCustomAttribute Method</span></span>
<span data-ttu-id="7c041-103">指定したオブジェクトに接続する、指定したメタデータ シグネチャを持つカスタム属性の定義を作成し、そのカスタム属性定義トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="7c041-103">Creates a definition for a custom attribute with the specified metadata signature, to be attached to the specified object, and gets a token to that custom attribute definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c041-104">構文</span><span class="sxs-lookup"><span data-stu-id="7c041-104">Syntax</span></span>  
  
```  
HRESULT DefineCustomAttribute (   
    [in]  mdToken     tkObj,   
    [in]  mdToken     tkType,   
    [in]  void const  *pCustomAttribute,   
    [in]  ULONG       cbCustomAttribute,   
    [out] mdCustomAttribute *pcv   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c041-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7c041-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="7c041-106">[in]所有者アイテムのトークンです。</span><span class="sxs-lookup"><span data-stu-id="7c041-106">[in] The token for the owner item.</span></span>  
  
 `tkType`  
 <span data-ttu-id="7c041-107">[in]カスタム属性を識別するトークンです。</span><span class="sxs-lookup"><span data-stu-id="7c041-107">[in] The token that identifies the custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="7c041-108">[in]カスタム属性へのポインター。</span><span class="sxs-lookup"><span data-stu-id="7c041-108">[in] A pointer to the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="7c041-109">[in]内のバイト数`pCustomAttribute`します。</span><span class="sxs-lookup"><span data-stu-id="7c041-109">[in] The count of bytes in `pCustomAttribute`.</span></span>  
  
 `pcv`  
 <span data-ttu-id="7c041-110">[out]`mdCustomAttribute`に割り当てられたトークン。</span><span class="sxs-lookup"><span data-stu-id="7c041-110">[out] The `mdCustomAttribute` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c041-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="7c041-111">Requirements</span></span>  
 <span data-ttu-id="7c041-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c041-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c041-113">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7c041-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7c041-114">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="7c041-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7c041-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c041-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c041-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="7c041-116">See also</span></span>

- [<span data-ttu-id="7c041-117">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7c041-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="7c041-118">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7c041-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
