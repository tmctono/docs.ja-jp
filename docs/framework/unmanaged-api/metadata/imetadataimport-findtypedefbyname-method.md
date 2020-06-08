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
ms.openlocfilehash: 5485f43afe08fafa559d0418327a8f4f186860e7
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491512"
---
# <a name="imetadataimportfindtypedefbyname-method"></a><span data-ttu-id="0dd16-102">IMetaDataImport::FindTypeDefByName メソッド</span><span class="sxs-lookup"><span data-stu-id="0dd16-102">IMetaDataImport::FindTypeDefByName Method</span></span>
<span data-ttu-id="0dd16-103">指定した名前を持つの TypeDef メタデータトークンへのポインターを取得し <xref:System.Type> ます。</span><span class="sxs-lookup"><span data-stu-id="0dd16-103">Gets a pointer to the TypeDef metadata token for the <xref:System.Type> with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0dd16-104">構文</span><span class="sxs-lookup"><span data-stu-id="0dd16-104">Syntax</span></span>  
  
```cpp  
HRESULT FindTypeDefByName  
   [in]  LPCWSTR       szTypeDef,  
   [in]  mdToken       tkEnclosingClass,  
   [out] mdTypeDef     *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0dd16-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0dd16-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="0dd16-106">からTypeDef トークンを取得する型の名前。</span><span class="sxs-lookup"><span data-stu-id="0dd16-106">[in] The name of the type for which to get the TypeDef token.</span></span>  
  
 `tkEnclosingClass`  
 <span data-ttu-id="0dd16-107">から外側のクラスを表す TypeDef または TypeRef トークン。</span><span class="sxs-lookup"><span data-stu-id="0dd16-107">[in] A TypeDef or TypeRef token representing the enclosing class.</span></span> <span data-ttu-id="0dd16-108">検索する型が入れ子になったクラスでない場合は、この値を NULL に設定します。</span><span class="sxs-lookup"><span data-stu-id="0dd16-108">If the type to find is not a nested class, set this value to NULL.</span></span>  
  
 `ptd`  
 <span data-ttu-id="0dd16-109">入出力一致する TypeDef トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="0dd16-109">[out] A pointer to the matching TypeDef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0dd16-110">要件</span><span class="sxs-lookup"><span data-stu-id="0dd16-110">Requirements</span></span>  
 <span data-ttu-id="0dd16-111">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0dd16-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0dd16-112">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="0dd16-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0dd16-113">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="0dd16-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0dd16-114">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0dd16-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dd16-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="0dd16-115">See also</span></span>

- [<span data-ttu-id="0dd16-116">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0dd16-116">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="0dd16-117">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0dd16-117">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
