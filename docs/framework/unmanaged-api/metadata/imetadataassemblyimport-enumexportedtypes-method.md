---
title: IMetaDataAssemblyImport::EnumExportedTypes メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumExportedTypes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumExportedTypes
helpviewer_keywords:
- EnumExportedTypes method [.NET Framework metadata]
- IMetaDataAssemblyImport::EnumExportedTypes method [.NET Framework metadata]
ms.assetid: e5912ed8-e4ce-438b-8ea3-d9e4c288d109
topic_type:
- apiref
ms.openlocfilehash: 45e2348b4726447548544d975e60b93e464fb402
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450330"
---
# <a name="imetadataassemblyimportenumexportedtypes-method"></a><span data-ttu-id="80d5e-102">IMetaDataAssemblyImport::EnumExportedTypes メソッド</span><span class="sxs-lookup"><span data-stu-id="80d5e-102">IMetaDataAssemblyImport::EnumExportedTypes Method</span></span>
<span data-ttu-id="80d5e-103">現在のメタデータスコープ内のアセンブリマニフェストで参照される、エクスポートされた型を列挙します。</span><span class="sxs-lookup"><span data-stu-id="80d5e-103">Enumerates the exported types referenced in the assembly manifest in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80d5e-104">構文</span><span class="sxs-lookup"><span data-stu-id="80d5e-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumExportedTypes (  
    [in, out] HCORENUM     *phEnum,   
    [out] mdExportedType   rExportedTypes[],   
    [in]  ULONG            cMax,   
    [out] ULONG            *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="80d5e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="80d5e-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="80d5e-106">[入力、出力]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="80d5e-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="80d5e-107">`EnumExportedTypes` メソッドを初めて呼び出すときは、null 値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80d5e-107">This must be a null value when the `EnumExportedTypes` method is called for the first time.</span></span>  
  
 `rExportedTypes`  
 <span data-ttu-id="80d5e-108">入出力`mdExportedType` メタデータトークンの列挙体。</span><span class="sxs-lookup"><span data-stu-id="80d5e-108">[out] The enumeration of `mdExportedType` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="80d5e-109">から`rExportedTypes` 配列に格納できる `mdExportedType` トークンの最大数。</span><span class="sxs-lookup"><span data-stu-id="80d5e-109">[in] The maximum number of `mdExportedType` tokens that can be placed in the `rExportedTypes` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="80d5e-110">入出力`rExportedTypes`に実際に配置されている `mdExportedType` トークンの数。</span><span class="sxs-lookup"><span data-stu-id="80d5e-110">[out] The number of `mdExportedType` tokens actually placed in `rExportedTypes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="80d5e-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="80d5e-111">Return Value</span></span>  
  
|<span data-ttu-id="80d5e-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="80d5e-112">HRESULT</span></span>|<span data-ttu-id="80d5e-113">説明</span><span class="sxs-lookup"><span data-stu-id="80d5e-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="80d5e-114">`EnumExportedTypes` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="80d5e-114">`EnumExportedTypes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="80d5e-115">列挙するトークンがありません。</span><span class="sxs-lookup"><span data-stu-id="80d5e-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="80d5e-116">この場合、`pcTokens` は0に設定されます。</span><span class="sxs-lookup"><span data-stu-id="80d5e-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="80d5e-117">要件</span><span class="sxs-lookup"><span data-stu-id="80d5e-117">Requirements</span></span>  
 <span data-ttu-id="80d5e-118">**プラットフォーム:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80d5e-118">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80d5e-119">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="80d5e-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="80d5e-120">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="80d5e-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="80d5e-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80d5e-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80d5e-122">参照</span><span class="sxs-lookup"><span data-stu-id="80d5e-122">See also</span></span>

- [<span data-ttu-id="80d5e-123">IMetaDataAssemblyImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="80d5e-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
