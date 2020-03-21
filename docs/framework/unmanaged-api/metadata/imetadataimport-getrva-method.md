---
title: IMetaDataImport::GetRVA メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetRVA
helpviewer_keywords:
- GetRVA method [.NET Framework metadata]
- IMetaDataImport::GetRVA method [.NET Framework metadata]
ms.assetid: ea422217-988b-4acd-b2db-c55357938275
topic_type:
- apiref
ms.openlocfilehash: 190bcacc84646cfd9294cf2b6b53b0474f38758f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177213"
---
# <a name="imetadataimportgetrva-method"></a><span data-ttu-id="189f3-102">IMetaDataImport::GetRVA メソッド</span><span class="sxs-lookup"><span data-stu-id="189f3-102">IMetaDataImport::GetRVA Method</span></span>
<span data-ttu-id="189f3-103">指定したトークンによって表されるメソッドまたはフィールドの相対仮想アドレス (RVA) および実装フラグを取得します。</span><span class="sxs-lookup"><span data-stu-id="189f3-103">Gets the relative virtual address (RVA) and the implementation flags of the method or field represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="189f3-104">構文</span><span class="sxs-lookup"><span data-stu-id="189f3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRVA (  
   [in]  mdToken     tk,
   [out] ULONG       *pulCodeRVA,
   [out]  DWORD      *pdwImplFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="189f3-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="189f3-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="189f3-106">[in]RVA を返すコード オブジェクトを表す MethodDef または FieldDef メタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="189f3-106">[in] A MethodDef or FieldDef metadata token that represents the code object to return the RVA for.</span></span> <span data-ttu-id="189f3-107">トークンが FieldDef の場合、フィールドはグローバル変数である必要があります。</span><span class="sxs-lookup"><span data-stu-id="189f3-107">If the token is a FieldDef, the field must be a global variable.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="189f3-108">[アウト]トークンによって表されるコード オブジェクトの相対仮想アドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="189f3-108">[out] A pointer to the relative virtual address of the code object represented by the token.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="189f3-109">[アウト]メソッドの実装フラグへのポインター。</span><span class="sxs-lookup"><span data-stu-id="189f3-109">[out] A pointer to the implementation flags for the method.</span></span> <span data-ttu-id="189f3-110">この値は[、CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md)列挙型のビットマスクです。</span><span class="sxs-lookup"><span data-stu-id="189f3-110">This value is a bitmask from the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration.</span></span> <span data-ttu-id="189f3-111">の値`pdwImplFlags`は、MethodDef`tk`トークンの場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="189f3-111">The value of `pdwImplFlags` is valid only if `tk` is a MethodDef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="189f3-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="189f3-112">Requirements</span></span>  
 <span data-ttu-id="189f3-113">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="189f3-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="189f3-114">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="189f3-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="189f3-115">**ライブラリ:** MsCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="189f3-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="189f3-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="189f3-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="189f3-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="189f3-117">See also</span></span>

- [<span data-ttu-id="189f3-118">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="189f3-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="189f3-119">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="189f3-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
