---
title: IMetaDataEmit::TranslateSigWithScope メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.TranslateSigWithScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::TranslateSigWithScope
helpviewer_keywords:
- TranslateSigWithScope method [.NET Framework metadata]
- IMetaDataEmit::TranslateSigWithScope method [.NET Framework metadata]
ms.assetid: 47915d33-b7bf-409e-b484-4ee1df15de22
topic_type:
- apiref
ms.openlocfilehash: cea84f47a5289df4bc9c50381e18d7077b3b8dad
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440479"
---
# <a name="imetadataemittranslatesigwithscope-method"></a><span data-ttu-id="ae552-102">IMetaDataEmit::TranslateSigWithScope メソッド</span><span class="sxs-lookup"><span data-stu-id="ae552-102">IMetaDataEmit::TranslateSigWithScope Method</span></span>
<span data-ttu-id="ae552-103">現在のスコープにアセンブリをインポートし、マージされたスコープの新しいメタデータシグネチャを取得します。</span><span class="sxs-lookup"><span data-stu-id="ae552-103">Imports an assembly into the current scope and gets a new metadata signature for the merged scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae552-104">構文</span><span class="sxs-lookup"><span data-stu-id="ae552-104">Syntax</span></span>  
  
```cpp  
HRESULT TranslateSigWithScope (   
    [in]  IMetaDataAssemblyImport   *pAssemImport,   
    [in]  const void                *pbHashValue,   
    [in]  ULONG                     cbHashValue,   
    [in]  IMetaDataImport           *import,   
    [in]  PCCOR_SIGNATURE           pbSigBlob,   
    [in]  ULONG                     cbSigBlob,  
    [in]  IMetaDataAssemblyEmit     *pAssemEmit,   
    [in]  IMetaDataEmit             *emit,   
    [out] PCOR_SIGNATURE            pvTranslatedSig,   
    [in]  ULONG                     cbTranslatedSigMax,   
    [out] ULONG                     *pcbTranslatedSig   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae552-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ae552-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="ae552-106">[in] (署名が定義されている) インポート アセンブリのインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="ae552-106">[in] The interface for import assembly (where the signature is defined).</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="ae552-107">からアセンブリのハッシュ blob。</span><span class="sxs-lookup"><span data-stu-id="ae552-107">[in] The hash blob for the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="ae552-108">から`pbHashValue`内のバイト数。</span><span class="sxs-lookup"><span data-stu-id="ae552-108">[in] The count of bytes in `pbHashValue`.</span></span>  
  
 `import`  
 <span data-ttu-id="ae552-109">からインポートメタデータスコープのインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="ae552-109">[in] The interface for import metadata scope.</span></span>  
  
 `pbSigBlob`  
 <span data-ttu-id="ae552-110">からインポートされる署名。</span><span class="sxs-lookup"><span data-stu-id="ae552-110">[in] The signature to be imported.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="ae552-111">から`pbSigBlob`のサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="ae552-111">[in] The size, in bytes, of `pbSigBlob`.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="ae552-112">からエクスポートアセンブリのインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="ae552-112">[in] The interface for export assembly.</span></span>  
  
 `emit`  
 <span data-ttu-id="ae552-113">からエクスポートメタデータスコープのインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="ae552-113">[in] The interface for export metadata scope.</span></span>  
  
 `pvTranslatedSig`  
 <span data-ttu-id="ae552-114">入出力変換された署名 blob を保持するバッファー。</span><span class="sxs-lookup"><span data-stu-id="ae552-114">[out] The buffer to hold the translated signature blob.</span></span>  
  
 `cbTranslatedSigMax`  
 <span data-ttu-id="ae552-115">から`pvTranslatedSig`の容量 (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="ae552-115">[in] The capacity, in bytes, of `pvTranslatedSig`.</span></span>  
  
 `pcbTranslatedSig`  
 <span data-ttu-id="ae552-116">入出力変換されたシグネチャの実際のバイト数。</span><span class="sxs-lookup"><span data-stu-id="ae552-116">[out] The number of actual bytes in the translated signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae552-117">要件</span><span class="sxs-lookup"><span data-stu-id="ae552-117">Requirements</span></span>  
 <span data-ttu-id="ae552-118">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae552-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae552-119">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="ae552-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ae552-120">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="ae552-120">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ae552-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae552-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae552-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="ae552-122">See also</span></span>

- [<span data-ttu-id="ae552-123">IMetaDataAssemblyEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ae552-123">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="ae552-124">IMetaDataAssemblyImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ae552-124">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="ae552-125">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ae552-125">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="ae552-126">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ae552-126">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="ae552-127">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ae552-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
