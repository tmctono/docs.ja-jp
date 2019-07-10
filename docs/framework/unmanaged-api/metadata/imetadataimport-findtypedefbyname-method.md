---
title: IMetaDataImport::FindTypeDefByName メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindTypeDefByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindTypeDefByName
helpviewer_keywords:
- FindTypeDefByName method [.NET Framework metadata]
- IMetaDataImport::FindTypeDefByName method [.NET Framework metadata]
ms.assetid: f4c2cd88-ac28-4bad-9ab1-2cf9d2de41e6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7f182dad17e28cc5d19393bb4e13d747e34249fb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782476"
---
# <a name="imetadataimportfindtypedefbyname-method"></a><span data-ttu-id="d1c3d-102">IMetaDataImport::FindTypeDefByName メソッド</span><span class="sxs-lookup"><span data-stu-id="d1c3d-102">IMetaDataImport::FindTypeDefByName Method</span></span>
<span data-ttu-id="d1c3d-103">トークンの TypeDef メタデータへのポインターを取得、<xref:System.Type>指定した名前。</span><span class="sxs-lookup"><span data-stu-id="d1c3d-103">Gets a pointer to the TypeDef metadata token for the <xref:System.Type> with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1c3d-104">構文</span><span class="sxs-lookup"><span data-stu-id="d1c3d-104">Syntax</span></span>  
  
```cpp  
HRESULT FindTypeDefByName  
   [in]  LPCWSTR       szTypeDef,  
   [in]  mdToken       tkEnclosingClass,  
   [out] mdTypeDef     *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d1c3d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d1c3d-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="d1c3d-106">[in]TypeDef トークンを取得する対象の型の名前。</span><span class="sxs-lookup"><span data-stu-id="d1c3d-106">[in] The name of the type for which to get the TypeDef token.</span></span>  
  
 `tkEnclosingClass`  
 <span data-ttu-id="d1c3d-107">[in]外側のクラスを表す TypeDef または TypeRef トークンです。</span><span class="sxs-lookup"><span data-stu-id="d1c3d-107">[in] A TypeDef or TypeRef token representing the enclosing class.</span></span> <span data-ttu-id="d1c3d-108">検索する型が入れ子になったクラスでない場合は、この値を NULL に設定します。</span><span class="sxs-lookup"><span data-stu-id="d1c3d-108">If the type to find is not a nested class, set this value to NULL.</span></span>  
  
 `ptd`  
 <span data-ttu-id="d1c3d-109">[out]一致する TypeDef トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d1c3d-109">[out] A pointer to the matching TypeDef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1c3d-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="d1c3d-110">Requirements</span></span>  
 <span data-ttu-id="d1c3d-111">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1c3d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1c3d-112">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d1c3d-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d1c3d-113">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="d1c3d-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d1c3d-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1c3d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1c3d-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="d1c3d-115">See also</span></span>

- [<span data-ttu-id="d1c3d-116">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d1c3d-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="d1c3d-117">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d1c3d-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
