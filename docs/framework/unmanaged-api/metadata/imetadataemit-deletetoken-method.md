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
ms.openlocfilehash: 78f3ea0d84c932732a752f3af2dc952100fef831
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009276"
---
# <a name="imetadataemitdeletetoken-method"></a><span data-ttu-id="a9ed7-102">IMetaDataEmit::DeleteToken メソッド</span><span class="sxs-lookup"><span data-stu-id="a9ed7-102">IMetaDataEmit::DeleteToken Method</span></span>
<span data-ttu-id="a9ed7-103">現在のメタデータスコープから指定されたトークンを削除します。</span><span class="sxs-lookup"><span data-stu-id="a9ed7-103">Deletes the specified token from the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9ed7-104">構文</span><span class="sxs-lookup"><span data-stu-id="a9ed7-104">Syntax</span></span>  
  
```cpp  
HRESULT DeleteToken (
    [in]  mdToken     tkObj
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a9ed7-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a9ed7-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="a9ed7-106">から削除するトークン。</span><span class="sxs-lookup"><span data-stu-id="a9ed7-106">[in] The token to be deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9ed7-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="a9ed7-107">Requirements</span></span>  
 <span data-ttu-id="a9ed7-108">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9ed7-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9ed7-109">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="a9ed7-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a9ed7-110">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="a9ed7-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a9ed7-111">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9ed7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9ed7-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="a9ed7-112">See also</span></span>

- [<span data-ttu-id="a9ed7-113">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a9ed7-113">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="a9ed7-114">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a9ed7-114">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
