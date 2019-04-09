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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1c32dcfe5d00e1d35f7c63aa98a33d26f6b179c6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59152686"
---
# <a name="imetadataassemblyimportenumexportedtypes-method"></a><span data-ttu-id="0d856-102">IMetaDataAssemblyImport::EnumExportedTypes メソッド</span><span class="sxs-lookup"><span data-stu-id="0d856-102">IMetaDataAssemblyImport::EnumExportedTypes Method</span></span>
<span data-ttu-id="0d856-103">現在のメタデータ スコープ内のアセンブリ マニフェストで参照されているエクスポートされた型を列挙します。</span><span class="sxs-lookup"><span data-stu-id="0d856-103">Enumerates the exported types referenced in the assembly manifest in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d856-104">構文</span><span class="sxs-lookup"><span data-stu-id="0d856-104">Syntax</span></span>  
  
```  
HRESULT EnumExportedTypes (  
    [in, out] HCORENUM     *phEnum,   
    [out] mdExportedType   rExportedTypes[],   
    [in]  ULONG            cMax,   
    [out] ULONG            *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0d856-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0d856-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="0d856-106">[入力、出力]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="0d856-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="0d856-107">これを null には値と、`EnumExportedTypes`メソッドは、最初に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="0d856-107">This must be a null value when the `EnumExportedTypes` method is called for the first time.</span></span>  
  
 `rExportedTypes`  
 <span data-ttu-id="0d856-108">[out]列挙体`mdExportedType`メタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="0d856-108">[out] The enumeration of `mdExportedType` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="0d856-109">[in]最大数`mdExportedType`トークン内に配置できる、`rExportedTypes`配列。</span><span class="sxs-lookup"><span data-stu-id="0d856-109">[in] The maximum number of `mdExportedType` tokens that can be placed in the `rExportedTypes` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="0d856-110">[out]数`mdExportedType`トークンが実際に配置`rExportedTypes`します。</span><span class="sxs-lookup"><span data-stu-id="0d856-110">[out] The number of `mdExportedType` tokens actually placed in `rExportedTypes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0d856-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="0d856-111">Return Value</span></span>  
  
|<span data-ttu-id="0d856-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0d856-112">HRESULT</span></span>|<span data-ttu-id="0d856-113">説明</span><span class="sxs-lookup"><span data-stu-id="0d856-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumExportedTypes` <span data-ttu-id="0d856-114">正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="0d856-114">returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="0d856-115">トークンを列挙することはありません。</span><span class="sxs-lookup"><span data-stu-id="0d856-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="0d856-116">この場合、 `pcTokens` 0 に設定されます。</span><span class="sxs-lookup"><span data-stu-id="0d856-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0d856-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="0d856-117">Requirements</span></span>  
 <span data-ttu-id="0d856-118">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d856-118">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d856-119">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0d856-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0d856-120">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="0d856-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="0d856-121">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="0d856-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0d856-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="0d856-122">See also</span></span>

- [<span data-ttu-id="0d856-123">IMetaDataAssemblyImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0d856-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
