---
title: IMetaDataEmit::DeleteToken メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DeleteToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DeleteToken
helpviewer_keywords:
- DeleteToken method [.NET Framework metadata]
- IMetaDataEmit::DeleteToken method [.NET Framework metadata]
ms.assetid: a4926d0a-261b-46b1-9994-82633661a64b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d85fb62936678f830ca7eaf26a97c36be5f23ac8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62050091"
---
# <a name="imetadataemitdeletetoken-method"></a><span data-ttu-id="6e601-102">IMetaDataEmit::DeleteToken メソッド</span><span class="sxs-lookup"><span data-stu-id="6e601-102">IMetaDataEmit::DeleteToken Method</span></span>
<span data-ttu-id="6e601-103">現在のメタデータ スコープから指定したトークンを削除します。</span><span class="sxs-lookup"><span data-stu-id="6e601-103">Deletes the specified token from the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e601-104">構文</span><span class="sxs-lookup"><span data-stu-id="6e601-104">Syntax</span></span>  
  
```  
HRESULT DeleteToken (   
    [in]  mdToken     tkObj   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6e601-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6e601-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="6e601-106">[in]削除するトークンです。</span><span class="sxs-lookup"><span data-stu-id="6e601-106">[in] The token to be deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e601-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="6e601-107">Requirements</span></span>  
 <span data-ttu-id="6e601-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e601-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e601-109">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6e601-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6e601-110">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="6e601-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6e601-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e601-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e601-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="6e601-112">See also</span></span>

- [<span data-ttu-id="6e601-113">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6e601-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="6e601-114">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6e601-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
