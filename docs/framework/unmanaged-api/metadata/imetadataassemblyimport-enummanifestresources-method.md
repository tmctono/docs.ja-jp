---
title: IMetaDataAssemblyImport::EnumManifestResources メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumManifestResources
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumManifestResources
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumManifestResources method [.NET Framework metadata]
- EnumManifestResources method [.NET Framework metadata]
ms.assetid: 9543b111-5705-40c9-935c-a3ffc7a581aa
topic_type:
- apiref
ms.openlocfilehash: 560a6adf85fab7f421b86cba52224d5b1bfe1089
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006260"
---
# <a name="imetadataassemblyimportenummanifestresources-method"></a><span data-ttu-id="4047a-102">IMetaDataAssemblyImport::EnumManifestResources メソッド</span><span class="sxs-lookup"><span data-stu-id="4047a-102">IMetaDataAssemblyImport::EnumManifestResources Method</span></span>
<span data-ttu-id="4047a-103">現在のアセンブリマニフェストで参照されているリソースの列挙子へのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="4047a-103">Gets a pointer to an enumerator for the resources referenced in the current assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4047a-104">構文</span><span class="sxs-lookup"><span data-stu-id="4047a-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumManifestResources (  
    [in, out] HCORENUM         *phEnum,
    [out] mdManifestResource   rManifestResources[],
    [in]  ULONG                cMax,
    [out] ULONG                *pcTokens  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="4047a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4047a-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="4047a-106">[入力、出力]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="4047a-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="4047a-107">メソッドを初めて呼び出すときは、null 値を指定する必要があり `EnumManifestResources` ます。</span><span class="sxs-lookup"><span data-stu-id="4047a-107">This must be a null value when the `EnumManifestResources` method is called for the first time.</span></span>  
  
 `rManifestResources`  
 <span data-ttu-id="4047a-108">入出力メタデータトークンを格納するために使用される配列 `mdManifestResource` 。</span><span class="sxs-lookup"><span data-stu-id="4047a-108">[out] The array used to store the `mdManifestResource` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="4047a-109">から`mdManifestResource`に格納できるトークンの最大数 `rManifestResources` 。</span><span class="sxs-lookup"><span data-stu-id="4047a-109">[in] The maximum number of `mdManifestResource` tokens that can be placed in `rManifestResources`.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="4047a-110">入出力`mdManifestResource`実際に配置されたトークンの数 `rManifestResources` 。</span><span class="sxs-lookup"><span data-stu-id="4047a-110">[out] The number of `mdManifestResource` tokens actually placed in `rManifestResources`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4047a-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="4047a-111">Return Value</span></span>  
  
|<span data-ttu-id="4047a-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4047a-112">HRESULT</span></span>|<span data-ttu-id="4047a-113">説明</span><span class="sxs-lookup"><span data-stu-id="4047a-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="4047a-114">`EnumManifestResources`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="4047a-114">`EnumManifestResources` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="4047a-115">列挙するトークンがありません。</span><span class="sxs-lookup"><span data-stu-id="4047a-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="4047a-116">この場合、 `pcTokens` は0に設定されます。</span><span class="sxs-lookup"><span data-stu-id="4047a-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4047a-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="4047a-117">Requirements</span></span>  
 <span data-ttu-id="4047a-118">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4047a-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4047a-119">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="4047a-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4047a-120">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="4047a-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4047a-121">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4047a-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4047a-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="4047a-122">See also</span></span>

- [<span data-ttu-id="4047a-123">IMetaDataAssemblyImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4047a-123">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
