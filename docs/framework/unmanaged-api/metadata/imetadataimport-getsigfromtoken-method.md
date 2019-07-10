---
title: IMetaDataImport::GetSigFromToken メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetSigFromToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetSigFromToken
helpviewer_keywords:
- IMetaDataImport::GetSigFromToken method [.NET Framework metadata]
- GetSigFromToken method [.NET Framework metadata]
ms.assetid: ab894dc4-f7b6-4afc-bfcb-582a4b7e53a2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2060a70e2a3ce355f43ade67e6d6843670e00ad3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778853"
---
# <a name="imetadataimportgetsigfromtoken-method"></a><span data-ttu-id="b96d1-102">IMetaDataImport::GetSigFromToken メソッド</span><span class="sxs-lookup"><span data-stu-id="b96d1-102">IMetaDataImport::GetSigFromToken Method</span></span>
<span data-ttu-id="b96d1-103">指定したトークンに関連付けられているバイナリ メタデータ シグネチャを取得します。</span><span class="sxs-lookup"><span data-stu-id="b96d1-103">Gets the binary metadata signature associated with the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b96d1-104">構文</span><span class="sxs-lookup"><span data-stu-id="b96d1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSigFromToken (   
   [in]   mdSignature        mdSig,   
   [out]  PCCOR_SIGNATURE    *ppvSig,   
   [out]  ULONG              *pcbSig   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b96d1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b96d1-105">Parameters</span></span>  
 `mdSig`  
 <span data-ttu-id="b96d1-106">[in]バイナリ メタデータ シグネチャを返すトークンです。</span><span class="sxs-lookup"><span data-stu-id="b96d1-106">[in] The token to return the binary metadata signature for.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="b96d1-107">[out]返されたメタデータ署名へのポインター。</span><span class="sxs-lookup"><span data-stu-id="b96d1-107">[out] A pointer to the returned metadata signature.</span></span>  
  
 `pcbSig`  
 <span data-ttu-id="b96d1-108">[out]バイナリ メタデータ シグネチャのバイト単位のサイズ。</span><span class="sxs-lookup"><span data-stu-id="b96d1-108">[out] The size in bytes of the binary metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b96d1-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="b96d1-109">Requirements</span></span>  
 <span data-ttu-id="b96d1-110">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b96d1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b96d1-111">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b96d1-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b96d1-112">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="b96d1-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b96d1-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b96d1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b96d1-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="b96d1-114">See also</span></span>

- [<span data-ttu-id="b96d1-115">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b96d1-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="b96d1-116">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b96d1-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
