---
title: IMetaDataImport::GetNestedClassProps メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetNestedClassProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetNestedClassProps
helpviewer_keywords:
- GetNestedClassProps method [.NET Framework metadata]
- IMetaDataImport::GetNestedClassProps method [.NET Framework metadata]
ms.assetid: 704d19f1-bdef-4745-af8c-6476eb246fb3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d7dd59c1e0e8b28c557910da3fd9c6489370cc62
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778954"
---
# <a name="imetadataimportgetnestedclassprops-method"></a><span data-ttu-id="4f020-102">IMetaDataImport::GetNestedClassProps メソッド</span><span class="sxs-lookup"><span data-stu-id="4f020-102">IMetaDataImport::GetNestedClassProps Method</span></span>
<span data-ttu-id="4f020-103">親の TypeDef トークンを取得<xref:System.Type>入れ子にされた型を指定します。</span><span class="sxs-lookup"><span data-stu-id="4f020-103">Gets the TypeDef token for the parent <xref:System.Type> of the specified nested type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f020-104">構文</span><span class="sxs-lookup"><span data-stu-id="4f020-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNestedClassProps (  
   [in]   mdTypeDef      tdNestedClass,  
   [out]  mdTypeDef      *ptdEnclosingClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4f020-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4f020-105">Parameters</span></span>  
 `tdNestedClass`  
 <span data-ttu-id="4f020-106">[in]TypeDef トークンを表す、<xref:System.Type>親クラスを返すためにトークン。</span><span class="sxs-lookup"><span data-stu-id="4f020-106">[in] A TypeDef token representing the <xref:System.Type> to return the parent class token for.</span></span>  
  
 `ptdEnclosingClass`  
 <span data-ttu-id="4f020-107">[out]TypeDef トークンへのポインター、<xref:System.Type>を`tdNestedClass`で入れ子になっています。</span><span class="sxs-lookup"><span data-stu-id="4f020-107">[out] A pointer to the TypeDef token for the <xref:System.Type> that `tdNestedClass` is nested in.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f020-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="4f020-108">Requirements</span></span>  
 <span data-ttu-id="4f020-109">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f020-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f020-110">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4f020-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4f020-111">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="4f020-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4f020-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f020-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f020-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="4f020-113">See also</span></span>

- [<span data-ttu-id="4f020-114">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4f020-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="4f020-115">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4f020-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
