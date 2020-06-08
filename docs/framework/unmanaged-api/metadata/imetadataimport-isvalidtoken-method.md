---
title: IMetaDataImport::IsValidToken メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.IsValidToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::IsValidToken
helpviewer_keywords:
- IMetaDataImport::IsValidToken method [.NET Framework metadata]
- IsValidToken method [.NET Framework metadata]
ms.assetid: aeb0fc63-9eff-4384-9284-cb9900572d74
topic_type:
- apiref
ms.openlocfilehash: 9190d021b801be951d214406dde7e6d76da15608
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503439"
---
# <a name="imetadataimportisvalidtoken-method"></a><span data-ttu-id="3200a-102">IMetaDataImport::IsValidToken メソッド</span><span class="sxs-lookup"><span data-stu-id="3200a-102">IMetaDataImport::IsValidToken Method</span></span>
<span data-ttu-id="3200a-103">指定したトークンが、コード オブジェクトへの有効な参照を保持しているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="3200a-103">Gets a value indicating whether the specified token holds a valid reference to a code object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3200a-104">構文</span><span class="sxs-lookup"><span data-stu-id="3200a-104">Syntax</span></span>  
  
```cpp  
BOOL IsValidToken (  
   [in] mdToken     tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3200a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3200a-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="3200a-106">から参照の有効性を確認するトークン。</span><span class="sxs-lookup"><span data-stu-id="3200a-106">[in] The token to check the reference validity for.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3200a-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="3200a-107">Return Value</span></span>  
 <span data-ttu-id="3200a-108">`true``tk`が現在のスコープ内の有効なメタデータトークンである場合は。</span><span class="sxs-lookup"><span data-stu-id="3200a-108">`true` if `tk` is a valid metadata token within the current scope.</span></span> <span data-ttu-id="3200a-109">それ以外の場合は `false`。</span><span class="sxs-lookup"><span data-stu-id="3200a-109">Otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3200a-110">要件</span><span class="sxs-lookup"><span data-stu-id="3200a-110">Requirements</span></span>  
 <span data-ttu-id="3200a-111">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3200a-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3200a-112">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="3200a-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3200a-113">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="3200a-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3200a-114">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3200a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3200a-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="3200a-115">See also</span></span>

- [<span data-ttu-id="3200a-116">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3200a-116">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="3200a-117">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3200a-117">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
