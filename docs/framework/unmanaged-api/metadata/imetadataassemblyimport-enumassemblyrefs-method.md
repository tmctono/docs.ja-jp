---
title: IMetaDataAssemblyImport::EnumAssemblyRefs メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumAssemblyRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumAssemblyRefs
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumAssemblyRefs method [.NET Framework metadata]
- EnumAssemblyRefs method [.NET Framework metadata]
ms.assetid: 8844d0dd-730e-4592-8a7b-c1462d312c70
topic_type:
- apiref
ms.openlocfilehash: 06b81615565a04db7d6cfef4da9b5372a85afd68
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450348"
---
# <a name="imetadataassemblyimportenumassemblyrefs-method"></a><span data-ttu-id="2a3e2-102">IMetaDataAssemblyImport::EnumAssemblyRefs メソッド</span><span class="sxs-lookup"><span data-stu-id="2a3e2-102">IMetaDataAssemblyImport::EnumAssemblyRefs Method</span></span>
<span data-ttu-id="2a3e2-103">アセンブリマニフェストで定義されている `mdAssemblyRef` インスタンスを列挙します。</span><span class="sxs-lookup"><span data-stu-id="2a3e2-103">Enumerates the `mdAssemblyRef` instances that are defined in the assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a3e2-104">構文</span><span class="sxs-lookup"><span data-stu-id="2a3e2-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumAssemblyRefs (  
    [in, out] HCORENUM        *phEnum,   
    [out]     mdAssemblyRef   rAssemblyRefs[],   
    [in]      ULONG           cMax,   
    [out]     ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a3e2-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2a3e2-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="2a3e2-106">[入力、出力]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="2a3e2-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="2a3e2-107">`EnumAssemblyRefs` メソッドを初めて呼び出すときは、null 値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a3e2-107">This must be a null value when the `EnumAssemblyRefs` method is called for the first time.</span></span>  
  
 `rAssemblyRefs`  
 <span data-ttu-id="2a3e2-108">入出力`mdAssemblyRef` メタデータトークンの列挙体。</span><span class="sxs-lookup"><span data-stu-id="2a3e2-108">[out] The enumeration of `mdAssemblyRef` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="2a3e2-109">から`rAssemblyRefs` 配列に格納できるトークンの最大数。</span><span class="sxs-lookup"><span data-stu-id="2a3e2-109">[in] The maximum number of tokens that can be placed in the `rAssemblyRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="2a3e2-110">入出力`rAssemblyRefs`に実際に配置されているトークンの数。</span><span class="sxs-lookup"><span data-stu-id="2a3e2-110">[out] The number of tokens actually placed in `rAssemblyRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2a3e2-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="2a3e2-111">Return Value</span></span>  
  
|<span data-ttu-id="2a3e2-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2a3e2-112">HRESULT</span></span>|<span data-ttu-id="2a3e2-113">説明</span><span class="sxs-lookup"><span data-stu-id="2a3e2-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="2a3e2-114">`EnumAssemblyRefs` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="2a3e2-114">`EnumAssemblyRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="2a3e2-115">列挙するトークンがありません。</span><span class="sxs-lookup"><span data-stu-id="2a3e2-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="2a3e2-116">この場合、`pcTokens` は0に設定されます。</span><span class="sxs-lookup"><span data-stu-id="2a3e2-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2a3e2-117">要件</span><span class="sxs-lookup"><span data-stu-id="2a3e2-117">Requirements</span></span>  
 <span data-ttu-id="2a3e2-118">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a3e2-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a3e2-119">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="2a3e2-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2a3e2-120">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="2a3e2-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2a3e2-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a3e2-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a3e2-122">参照</span><span class="sxs-lookup"><span data-stu-id="2a3e2-122">See also</span></span>

- [<span data-ttu-id="2a3e2-123">IMetaDataAssemblyImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2a3e2-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
