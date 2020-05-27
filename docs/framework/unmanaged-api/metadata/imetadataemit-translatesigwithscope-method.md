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
ms.openlocfilehash: 7ef6dbc46806febc6fba89b39a8b894377225c23
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84003970"
---
# <a name="imetadataemittranslatesigwithscope-method"></a><span data-ttu-id="bbd26-102">IMetaDataEmit::TranslateSigWithScope メソッド</span><span class="sxs-lookup"><span data-stu-id="bbd26-102">IMetaDataEmit::TranslateSigWithScope Method</span></span>
<span data-ttu-id="bbd26-103">現在のスコープにアセンブリをインポートし、マージされたスコープの新しいメタデータシグネチャを取得します。</span><span class="sxs-lookup"><span data-stu-id="bbd26-103">Imports an assembly into the current scope and gets a new metadata signature for the merged scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbd26-104">構文</span><span class="sxs-lookup"><span data-stu-id="bbd26-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="bbd26-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bbd26-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="bbd26-106">からインポートアセンブリのインターフェイス (シグネチャが定義されている場合)。</span><span class="sxs-lookup"><span data-stu-id="bbd26-106">[in] The interface for import assembly (where the signature is defined).</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="bbd26-107">からアセンブリのハッシュ blob。</span><span class="sxs-lookup"><span data-stu-id="bbd26-107">[in] The hash blob for the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="bbd26-108">からのバイト数 `pbHashValue` 。</span><span class="sxs-lookup"><span data-stu-id="bbd26-108">[in] The count of bytes in `pbHashValue`.</span></span>  
  
 `import`  
 <span data-ttu-id="bbd26-109">からインポートメタデータスコープのインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="bbd26-109">[in] The interface for import metadata scope.</span></span>  
  
 `pbSigBlob`  
 <span data-ttu-id="bbd26-110">からインポートされる署名。</span><span class="sxs-lookup"><span data-stu-id="bbd26-110">[in] The signature to be imported.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="bbd26-111">からのサイズ (バイト単位) `pbSigBlob` 。</span><span class="sxs-lookup"><span data-stu-id="bbd26-111">[in] The size, in bytes, of `pbSigBlob`.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="bbd26-112">からエクスポートアセンブリのインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="bbd26-112">[in] The interface for export assembly.</span></span>  
  
 `emit`  
 <span data-ttu-id="bbd26-113">からエクスポートメタデータスコープのインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="bbd26-113">[in] The interface for export metadata scope.</span></span>  
  
 `pvTranslatedSig`  
 <span data-ttu-id="bbd26-114">入出力変換された署名 blob を保持するバッファー。</span><span class="sxs-lookup"><span data-stu-id="bbd26-114">[out] The buffer to hold the translated signature blob.</span></span>  
  
 `cbTranslatedSigMax`  
 <span data-ttu-id="bbd26-115">からの容量 (バイト単位) `pvTranslatedSig` 。</span><span class="sxs-lookup"><span data-stu-id="bbd26-115">[in] The capacity, in bytes, of `pvTranslatedSig`.</span></span>  
  
 `pcbTranslatedSig`  
 <span data-ttu-id="bbd26-116">入出力変換されたシグネチャの実際のバイト数。</span><span class="sxs-lookup"><span data-stu-id="bbd26-116">[out] The number of actual bytes in the translated signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bbd26-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="bbd26-117">Requirements</span></span>  
 <span data-ttu-id="bbd26-118">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bbd26-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bbd26-119">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="bbd26-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bbd26-120">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="bbd26-120">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bbd26-121">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bbd26-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbd26-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="bbd26-122">See also</span></span>

- [<span data-ttu-id="bbd26-123">IMetaDataAssemblyEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bbd26-123">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
- [<span data-ttu-id="bbd26-124">IMetaDataAssemblyImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bbd26-124">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
- [<span data-ttu-id="bbd26-125">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bbd26-125">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="bbd26-126">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bbd26-126">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="bbd26-127">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bbd26-127">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
