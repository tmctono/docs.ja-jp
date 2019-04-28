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
ms.openlocfilehash: eb5820087001a207af0c2552f91b4c17f5f78ff7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777658"
---
# <a name="imetadataimportgetnestedclassprops-method"></a><span data-ttu-id="968c6-102">IMetaDataImport::GetNestedClassProps メソッド</span><span class="sxs-lookup"><span data-stu-id="968c6-102">IMetaDataImport::GetNestedClassProps Method</span></span>
<span data-ttu-id="968c6-103">親の TypeDef トークンを取得<xref:System.Type>入れ子にされた型を指定します。</span><span class="sxs-lookup"><span data-stu-id="968c6-103">Gets the TypeDef token for the parent <xref:System.Type> of the specified nested type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="968c6-104">構文</span><span class="sxs-lookup"><span data-stu-id="968c6-104">Syntax</span></span>  
  
```  
HRESULT GetNestedClassProps (  
   [in]   mdTypeDef      tdNestedClass,  
   [out]  mdTypeDef      *ptdEnclosingClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="968c6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="968c6-105">Parameters</span></span>  
 `tdNestedClass`  
 <span data-ttu-id="968c6-106">[in]TypeDef トークンを表す、<xref:System.Type>親クラスを返すためにトークン。</span><span class="sxs-lookup"><span data-stu-id="968c6-106">[in] A TypeDef token representing the <xref:System.Type> to return the parent class token for.</span></span>  
  
 `ptdEnclosingClass`  
 <span data-ttu-id="968c6-107">[out]TypeDef トークンへのポインター、<xref:System.Type>を`tdNestedClass`で入れ子になっています。</span><span class="sxs-lookup"><span data-stu-id="968c6-107">[out] A pointer to the TypeDef token for the <xref:System.Type> that `tdNestedClass` is nested in.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="968c6-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="968c6-108">Requirements</span></span>  
 <span data-ttu-id="968c6-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="968c6-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="968c6-110">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="968c6-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="968c6-111">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="968c6-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="968c6-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="968c6-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="968c6-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="968c6-113">See also</span></span>

- [<span data-ttu-id="968c6-114">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="968c6-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="968c6-115">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="968c6-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
