---
title: IMetaDataEmit::GetTokenFromSig メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.GetTokenFromSig
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::GetTokenFromSig
helpviewer_keywords:
- IMetaDataEmit::GetTokenFromSig method [.NET Framework metadata]
- GetTokenFromSig method [.NET Framework metadata]
ms.assetid: 50a58a83-6287-40a4-b315-47823cea0a5c
topic_type:
- apiref
ms.openlocfilehash: f1262181fa745e1b6d3fc48a4ad728c1020705b5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434317"
---
# <a name="imetadataemitgettokenfromsig-method"></a><span data-ttu-id="177d0-102">IMetaDataEmit::GetTokenFromSig メソッド</span><span class="sxs-lookup"><span data-stu-id="177d0-102">IMetaDataEmit::GetTokenFromSig Method</span></span>
<span data-ttu-id="177d0-103">指定したメタデータシグネチャのトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="177d0-103">Gets a token for the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="177d0-104">構文</span><span class="sxs-lookup"><span data-stu-id="177d0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTokenFromSig (   
    [in]  PCCOR_SIGNATURE pvSig,   
    [in]  ULONG       cbSig,   
    [out] mdSignature *pmsig   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="177d0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="177d0-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="177d0-106">から永続化および格納される署名。</span><span class="sxs-lookup"><span data-stu-id="177d0-106">[in] The signature to be persisted and stored.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="177d0-107">から`pvSig`内のバイト数。</span><span class="sxs-lookup"><span data-stu-id="177d0-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `pmsig`  
 <span data-ttu-id="177d0-108">入出力割り当てられた `mdSignature` トークン。</span><span class="sxs-lookup"><span data-stu-id="177d0-108">[out] The `mdSignature` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="177d0-109">要件</span><span class="sxs-lookup"><span data-stu-id="177d0-109">Requirements</span></span>  
 <span data-ttu-id="177d0-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="177d0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="177d0-111">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="177d0-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="177d0-112">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="177d0-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="177d0-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="177d0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="177d0-114">参照</span><span class="sxs-lookup"><span data-stu-id="177d0-114">See also</span></span>

- [<span data-ttu-id="177d0-115">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="177d0-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="177d0-116">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="177d0-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
