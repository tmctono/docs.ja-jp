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
ms.openlocfilehash: d795f90c458b7fcf1a191b2763ac5f5bb55fb438
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490902"
---
# <a name="imetadataimportgetsigfromtoken-method"></a><span data-ttu-id="a0ae2-102">IMetaDataImport::GetSigFromToken メソッド</span><span class="sxs-lookup"><span data-stu-id="a0ae2-102">IMetaDataImport::GetSigFromToken Method</span></span>
<span data-ttu-id="a0ae2-103">指定したトークンに関連付けられているバイナリ メタデータ シグネチャを取得します。</span><span class="sxs-lookup"><span data-stu-id="a0ae2-103">Gets the binary metadata signature associated with the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0ae2-104">構文</span><span class="sxs-lookup"><span data-stu-id="a0ae2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSigFromToken (
   [in]   mdSignature        mdSig,
   [out]  PCCOR_SIGNATURE    *ppvSig,
   [out]  ULONG              *pcbSig
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0ae2-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a0ae2-105">Parameters</span></span>  
 `mdSig`  
 <span data-ttu-id="a0ae2-106">からバイナリメタデータシグネチャを返すトークン。</span><span class="sxs-lookup"><span data-stu-id="a0ae2-106">[in] The token to return the binary metadata signature for.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="a0ae2-107">入出力返されたメタデータシグネチャへのポインター。</span><span class="sxs-lookup"><span data-stu-id="a0ae2-107">[out] A pointer to the returned metadata signature.</span></span>  
  
 `pcbSig`  
 <span data-ttu-id="a0ae2-108">入出力バイナリメタデータシグネチャのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="a0ae2-108">[out] The size in bytes of the binary metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0ae2-109">要件</span><span class="sxs-lookup"><span data-stu-id="a0ae2-109">Requirements</span></span>  
 <span data-ttu-id="a0ae2-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0ae2-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0ae2-111">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="a0ae2-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a0ae2-112">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="a0ae2-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a0ae2-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0ae2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0ae2-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="a0ae2-114">See also</span></span>

- [<span data-ttu-id="a0ae2-115">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a0ae2-115">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="a0ae2-116">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a0ae2-116">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
