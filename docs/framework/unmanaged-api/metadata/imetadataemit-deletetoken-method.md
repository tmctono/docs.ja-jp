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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59138243"
---
# <a name="imetadataemitdeletetoken-method"></a><span data-ttu-id="5b7fc-102">IMetaDataEmit::DeleteToken メソッド</span><span class="sxs-lookup"><span data-stu-id="5b7fc-102">IMetaDataEmit::DeleteToken Method</span></span>
<span data-ttu-id="5b7fc-103">現在のメタデータ スコープから指定したトークンを削除します。</span><span class="sxs-lookup"><span data-stu-id="5b7fc-103">Deletes the specified token from the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b7fc-104">構文</span><span class="sxs-lookup"><span data-stu-id="5b7fc-104">Syntax</span></span>  
  
```  
HRESULT DeleteToken (   
    [in]  mdToken     tkObj   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b7fc-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5b7fc-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="5b7fc-106">[in]削除するトークンです。</span><span class="sxs-lookup"><span data-stu-id="5b7fc-106">[in] The token to be deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b7fc-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="5b7fc-107">Requirements</span></span>  
 <span data-ttu-id="5b7fc-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b7fc-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b7fc-109">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5b7fc-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5b7fc-110">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="5b7fc-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="5b7fc-111">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="5b7fc-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5b7fc-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="5b7fc-112">See also</span></span>

- [<span data-ttu-id="5b7fc-113">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5b7fc-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="5b7fc-114">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5b7fc-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
