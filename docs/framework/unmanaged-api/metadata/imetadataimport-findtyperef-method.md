---
title: IMetaDataImport::FindTypeRef メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindTypeRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindTypeRef
helpviewer_keywords:
- IMetaDataImport::FindTypeRef method [.NET Framework metadata]
- FindTypeRef method [.NET Framework metadata]
ms.assetid: 1b2bbf3f-943e-412e-b66c-e802431b055c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8159b5245598993a2075fb402b280f9ab4cb2cfa
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782457"
---
# <a name="imetadataimportfindtyperef-method"></a><span data-ttu-id="ecdfa-102">IMetaDataImport::FindTypeRef メソッド</span><span class="sxs-lookup"><span data-stu-id="ecdfa-102">IMetaDataImport::FindTypeRef Method</span></span>
<span data-ttu-id="ecdfa-103">トークンにポインターを取得、<xref:System.Type>参照を指定されたスコープ内にあるし、指定した名前を持ちます。</span><span class="sxs-lookup"><span data-stu-id="ecdfa-103">Gets a pointer to the TypeRef token for the <xref:System.Type> reference that is in the specified scope and that has the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecdfa-104">構文</span><span class="sxs-lookup"><span data-stu-id="ecdfa-104">Syntax</span></span>  
  
```cpp  
HRESULT FindTypeRef (  
   [in] mdToken        tkResolutionScope,  
   [in]  LPCWSTR       szName,  
   [out] mdTypeRef     *ptr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ecdfa-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ecdfa-105">Parameters</span></span>  
 `tkResolutionScope`  
 <span data-ttu-id="ecdfa-106">[in]モジュール、アセンブリ、または型を指定する ModuleRef、AssemblyRef、または TypeRef トークンそれぞれ、型参照を定義します。</span><span class="sxs-lookup"><span data-stu-id="ecdfa-106">[in] A ModuleRef, AssemblyRef, or TypeRef token that specifies the module, assembly, or type, respectively, in which the type reference is defined.</span></span>  
  
 `szName`  
 <span data-ttu-id="ecdfa-107">[in]検索する型参照の名前。</span><span class="sxs-lookup"><span data-stu-id="ecdfa-107">[in] The name of the type reference to search for.</span></span>  
  
 `ptr`  
 <span data-ttu-id="ecdfa-108">[out]一致する TypeRef トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="ecdfa-108">[out] A pointer to the matching TypeRef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ecdfa-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="ecdfa-109">Requirements</span></span>  
 <span data-ttu-id="ecdfa-110">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ecdfa-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecdfa-111">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ecdfa-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ecdfa-112">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="ecdfa-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ecdfa-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ecdfa-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecdfa-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="ecdfa-114">See also</span></span>

- [<span data-ttu-id="ecdfa-115">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ecdfa-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="ecdfa-116">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ecdfa-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
