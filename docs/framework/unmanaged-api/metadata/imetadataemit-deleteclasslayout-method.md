---
title: IMetaDataEmit::DeleteClassLayout メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DeleteClassLayout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DeleteClassLayout
helpviewer_keywords:
- DeleteClassLayout method [.NET Framework metadata]
- IMetaDataEmit::DeleteClassLayout method [.NET Framework metadata]
ms.assetid: 65a4ad49-fa49-4b36-8ed1-76dd6a185ab4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a195daf2aa1b1c5a8f9c4335f7c4185f30093360
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59178530"
---
# <a name="imetadataemitdeleteclasslayout-method"></a><span data-ttu-id="be3dd-102">IMetaDataEmit::DeleteClassLayout メソッド</span><span class="sxs-lookup"><span data-stu-id="be3dd-102">IMetaDataEmit::DeleteClassLayout Method</span></span>
<span data-ttu-id="be3dd-103">指定したトークンによって表される型のクラス レイアウト メタデータ シグネチャを破棄します。</span><span class="sxs-lookup"><span data-stu-id="be3dd-103">Destroys the class layout metadata signature for the type represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be3dd-104">構文</span><span class="sxs-lookup"><span data-stu-id="be3dd-104">Syntax</span></span>  
  
```  
HRESULT DeleteClassLayout (  
    [in]  mdTypeDef   td  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="be3dd-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="be3dd-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="be3dd-106">[in]`mdTypeDef`クラス レイアウトを削除する対象の型を表すメタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="be3dd-106">[in] An `mdTypeDef` metadata token that represents the type for which the class layout will be deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be3dd-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="be3dd-107">Requirements</span></span>  
 <span data-ttu-id="be3dd-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="be3dd-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be3dd-109">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="be3dd-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="be3dd-110">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="be3dd-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="be3dd-111">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="be3dd-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="be3dd-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="be3dd-112">See also</span></span>

- [<span data-ttu-id="be3dd-113">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="be3dd-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="be3dd-114">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="be3dd-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
