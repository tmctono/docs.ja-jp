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
ms.openlocfilehash: 823a172c05d2ce76fef790966f54d7216f579fde
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59152985"
---
# <a name="imetadataimportgetsigfromtoken-method"></a><span data-ttu-id="64b69-102">IMetaDataImport::GetSigFromToken メソッド</span><span class="sxs-lookup"><span data-stu-id="64b69-102">IMetaDataImport::GetSigFromToken Method</span></span>
<span data-ttu-id="64b69-103">指定したトークンに関連付けられているバイナリ メタデータ シグネチャを取得します。</span><span class="sxs-lookup"><span data-stu-id="64b69-103">Gets the binary metadata signature associated with the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64b69-104">構文</span><span class="sxs-lookup"><span data-stu-id="64b69-104">Syntax</span></span>  
  
```  
HRESULT GetSigFromToken (   
   [in]   mdSignature        mdSig,   
   [out]  PCCOR_SIGNATURE    *ppvSig,   
   [out]  ULONG              *pcbSig   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="64b69-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="64b69-105">Parameters</span></span>  
 `mdSig`  
 <span data-ttu-id="64b69-106">[in]バイナリ メタデータ シグネチャを返すトークンです。</span><span class="sxs-lookup"><span data-stu-id="64b69-106">[in] The token to return the binary metadata signature for.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="64b69-107">[out]返されたメタデータ署名へのポインター。</span><span class="sxs-lookup"><span data-stu-id="64b69-107">[out] A pointer to the returned metadata signature.</span></span>  
  
 `pcbSig`  
 <span data-ttu-id="64b69-108">[out]バイナリ メタデータ シグネチャのバイト単位のサイズ。</span><span class="sxs-lookup"><span data-stu-id="64b69-108">[out] The size in bytes of the binary metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64b69-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="64b69-109">Requirements</span></span>  
 <span data-ttu-id="64b69-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="64b69-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64b69-111">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="64b69-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="64b69-112">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="64b69-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="64b69-113">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="64b69-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="64b69-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="64b69-114">See also</span></span>

- [<span data-ttu-id="64b69-115">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="64b69-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="64b69-116">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="64b69-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
