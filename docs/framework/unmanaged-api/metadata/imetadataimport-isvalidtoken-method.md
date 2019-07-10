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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 753449924f3415eb826b59d3a887eb69b9efba39
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778781"
---
# <a name="imetadataimportisvalidtoken-method"></a><span data-ttu-id="20954-102">IMetaDataImport::IsValidToken メソッド</span><span class="sxs-lookup"><span data-stu-id="20954-102">IMetaDataImport::IsValidToken Method</span></span>
<span data-ttu-id="20954-103">指定したトークンが、コード オブジェクトへの有効な参照を保持しているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="20954-103">Gets a value indicating whether the specified token holds a valid reference to a code object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20954-104">構文</span><span class="sxs-lookup"><span data-stu-id="20954-104">Syntax</span></span>  
  
```cpp  
BOOL IsValidToken (  
   [in] mdToken     tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="20954-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="20954-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="20954-106">[in]参照の有効性を確認するトークン。</span><span class="sxs-lookup"><span data-stu-id="20954-106">[in] The token to check the reference validity for.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="20954-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="20954-107">Return Value</span></span>  
 <span data-ttu-id="20954-108">`true` 場合`tk`は現在のスコープ内で有効なメタデータ トークンです。</span><span class="sxs-lookup"><span data-stu-id="20954-108">`true` if `tk` is a valid metadata token within the current scope.</span></span> <span data-ttu-id="20954-109">それ以外の場合は `false`。</span><span class="sxs-lookup"><span data-stu-id="20954-109">Otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20954-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="20954-110">Requirements</span></span>  
 <span data-ttu-id="20954-111">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="20954-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20954-112">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="20954-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="20954-113">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="20954-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="20954-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20954-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20954-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="20954-115">See also</span></span>

- [<span data-ttu-id="20954-116">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="20954-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="20954-117">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="20954-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
