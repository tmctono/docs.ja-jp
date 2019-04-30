---
title: IMetaDataDispenserEx::FindAssembly メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.FindAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::FindAssembly
helpviewer_keywords:
- FindAssembly method [.NET Framework metadata]
- IMetaDataDispenserEx::FindAssembly method [.NET Framework metadata]
ms.assetid: 3afe7252-5f28-48d9-a74d-1927566c404c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d204ec29304fe0c4596950cd17c48d0c1d2ac616
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62050156"
---
# <a name="imetadatadispenserexfindassembly-method"></a><span data-ttu-id="55f1e-102">IMetaDataDispenserEx::FindAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="55f1e-102">IMetaDataDispenserEx::FindAssembly Method</span></span>
<span data-ttu-id="55f1e-103">このメソッドは実装されていません。</span><span class="sxs-lookup"><span data-stu-id="55f1e-103">This method is not implemented.</span></span> <span data-ttu-id="55f1e-104">呼び出された場合、E_NOTIMPL を返します。</span><span class="sxs-lookup"><span data-stu-id="55f1e-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55f1e-105">構文</span><span class="sxs-lookup"><span data-stu-id="55f1e-105">Syntax</span></span>  
  
```  
HRESULT FindAssembly(  
    [in]  LPCWSTR  szAppBase,  
    [in]  LPCWSTR  szPrivateBin,  
    [in]  LPCWSTR  szGlobalBin,  
    [in]  LPCWSTR  szAssemblyName,  
    [out] LPCWSTR  szName,  
    [in]  ULONG    cchName,  
    [out] ULONG    *pcName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55f1e-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="55f1e-106">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="55f1e-107">[in]使用されません。</span><span class="sxs-lookup"><span data-stu-id="55f1e-107">[in] Not used.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="55f1e-108">[in]使用されません。</span><span class="sxs-lookup"><span data-stu-id="55f1e-108">[in] Not used.</span></span>  
  
 `szGlobalBin`  
 <span data-ttu-id="55f1e-109">[in]使用されません。</span><span class="sxs-lookup"><span data-stu-id="55f1e-109">[in] Not used.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="55f1e-110">[in]検索するアセンブリ。</span><span class="sxs-lookup"><span data-stu-id="55f1e-110">[in] The assembly to be found.</span></span>  
  
 `szName`  
 <span data-ttu-id="55f1e-111">[out]アセンブリの簡易名。</span><span class="sxs-lookup"><span data-stu-id="55f1e-111">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="55f1e-112">[in]サイズ (バイト単位) の`szName`します。</span><span class="sxs-lookup"><span data-stu-id="55f1e-112">[in] The size, in bytes, of `szName`.</span></span>  
  
 `pcName`  
 <span data-ttu-id="55f1e-113">[out]実際に返される文字数`szName`します。</span><span class="sxs-lookup"><span data-stu-id="55f1e-113">[out] The number of characters actually returned in `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55f1e-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="55f1e-114">Requirements</span></span>  
 <span data-ttu-id="55f1e-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="55f1e-115">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55f1e-116">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="55f1e-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="55f1e-117">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="55f1e-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="55f1e-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55f1e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55f1e-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="55f1e-119">See also</span></span>

- [<span data-ttu-id="55f1e-120">IMetaDataDispenserEx インターフェイス</span><span class="sxs-lookup"><span data-stu-id="55f1e-120">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="55f1e-121">IMetaDataDispenser インターフェイス</span><span class="sxs-lookup"><span data-stu-id="55f1e-121">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
