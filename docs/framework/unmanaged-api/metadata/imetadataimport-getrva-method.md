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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d305aa59c1b9e9e1225b30f12e36fc689d584db1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778887"
---
# <a name="imetadataimportgetrva-method"></a><span data-ttu-id="fb15f-102">IMetaDataImport::GetRVA メソッド</span><span class="sxs-lookup"><span data-stu-id="fb15f-102">IMetaDataImport::GetRVA Method</span></span>
<span data-ttu-id="fb15f-103">相対仮想アドレス (RVA) と、メソッド、または指定したトークンによって表されるフィールドの実装フラグを取得します。</span><span class="sxs-lookup"><span data-stu-id="fb15f-103">Gets the relative virtual address (RVA) and the implementation flags of the method or field represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb15f-104">構文</span><span class="sxs-lookup"><span data-stu-id="fb15f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRVA (  
   [in]  mdToken     tk,   
   [out] ULONG       *pulCodeRVA,   
   [out]  DWORD      *pdwImplFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fb15f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fb15f-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="fb15f-106">[in]RVA を返すコード オブジェクトを表す MethodDef または FieldDef メタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="fb15f-106">[in] A MethodDef or FieldDef metadata token that represents the code object to return the RVA for.</span></span> <span data-ttu-id="fb15f-107">トークンが、FieldDef の場合は、フィールドは、グローバル変数である必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb15f-107">If the token is a FieldDef, the field must be a global variable.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="fb15f-108">[out]トークンが表すコード オブジェクトの相対仮想アドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="fb15f-108">[out] A pointer to the relative virtual address of the code object represented by the token.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="fb15f-109">[out]メソッドの実装フラグへのポインター。</span><span class="sxs-lookup"><span data-stu-id="fb15f-109">[out] A pointer to the implementation flags for the method.</span></span> <span data-ttu-id="fb15f-110">この値はビットマスクから、 [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md)列挙体。</span><span class="sxs-lookup"><span data-stu-id="fb15f-110">This value is a bitmask from the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration.</span></span> <span data-ttu-id="fb15f-111">値`pdwImplFlags`は有効な場合にのみ`tk`MethodDef トークンです。</span><span class="sxs-lookup"><span data-stu-id="fb15f-111">The value of `pdwImplFlags` is valid only if `tk` is a MethodDef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb15f-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="fb15f-112">Requirements</span></span>  
 <span data-ttu-id="fb15f-113">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb15f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb15f-114">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="fb15f-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fb15f-115">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="fb15f-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fb15f-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb15f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb15f-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="fb15f-117">See also</span></span>

- [<span data-ttu-id="fb15f-118">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fb15f-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="fb15f-119">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fb15f-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
