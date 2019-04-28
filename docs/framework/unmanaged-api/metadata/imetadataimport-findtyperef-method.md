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
ms.openlocfilehash: acc006894f05536ed76bac60b0fde9277a460813
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777846"
---
# <a name="imetadataimportfindtyperef-method"></a><span data-ttu-id="71041-102">IMetaDataImport::FindTypeRef メソッド</span><span class="sxs-lookup"><span data-stu-id="71041-102">IMetaDataImport::FindTypeRef Method</span></span>
<span data-ttu-id="71041-103">トークンにポインターを取得、<xref:System.Type>参照を指定されたスコープ内にあるし、指定した名前を持ちます。</span><span class="sxs-lookup"><span data-stu-id="71041-103">Gets a pointer to the TypeRef token for the <xref:System.Type> reference that is in the specified scope and that has the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71041-104">構文</span><span class="sxs-lookup"><span data-stu-id="71041-104">Syntax</span></span>  
  
```  
HRESULT FindTypeRef (  
   [in] mdToken        tkResolutionScope,  
   [in]  LPCWSTR       szName,  
   [out] mdTypeRef     *ptr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71041-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="71041-105">Parameters</span></span>  
 `tkResolutionScope`  
 <span data-ttu-id="71041-106">[in]モジュール、アセンブリ、または型を指定する ModuleRef、AssemblyRef、または TypeRef トークンそれぞれ、型参照を定義します。</span><span class="sxs-lookup"><span data-stu-id="71041-106">[in] A ModuleRef, AssemblyRef, or TypeRef token that specifies the module, assembly, or type, respectively, in which the type reference is defined.</span></span>  
  
 `szName`  
 <span data-ttu-id="71041-107">[in]検索する型参照の名前。</span><span class="sxs-lookup"><span data-stu-id="71041-107">[in] The name of the type reference to search for.</span></span>  
  
 `ptr`  
 <span data-ttu-id="71041-108">[out]一致する TypeRef トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="71041-108">[out] A pointer to the matching TypeRef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71041-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="71041-109">Requirements</span></span>  
 <span data-ttu-id="71041-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="71041-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71041-111">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="71041-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="71041-112">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="71041-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="71041-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71041-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71041-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="71041-114">See also</span></span>

- [<span data-ttu-id="71041-115">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="71041-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="71041-116">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="71041-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
