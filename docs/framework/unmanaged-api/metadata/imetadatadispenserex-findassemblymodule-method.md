---
title: IMetaDataDispenserEx::FindAssemblyModule メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.FindAssemblyModule
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::FindAssemblyModule
helpviewer_keywords:
- FindAssemblyModule method [.NET Framework metadata]
- IMetaDataDispenserEx::FindAssemblyModule method [.NET Framework metadata]
ms.assetid: d1fb65e1-7e19-4513-85b1-44f87c294d3e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2d1d97e443be884f45187a2811ddfce106249515
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62044357"
---
# <a name="imetadatadispenserexfindassemblymodule-method"></a><span data-ttu-id="ee0b7-102">IMetaDataDispenserEx::FindAssemblyModule メソッド</span><span class="sxs-lookup"><span data-stu-id="ee0b7-102">IMetaDataDispenserEx::FindAssemblyModule Method</span></span>
<span data-ttu-id="ee0b7-103">このメソッドは実装されていません。</span><span class="sxs-lookup"><span data-stu-id="ee0b7-103">This method is not implemented.</span></span> <span data-ttu-id="ee0b7-104">呼び出された場合、E_NOTIMPL を返します。</span><span class="sxs-lookup"><span data-stu-id="ee0b7-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee0b7-105">構文</span><span class="sxs-lookup"><span data-stu-id="ee0b7-105">Syntax</span></span>  
  
```  
HRESULT FindAssemblyModule(  
    [in]  LPCWSTR  szAppBase,  
    [in]  LPCWSTR  szPrivateBin,  
    [in]  LPCWSTR  szGlobalBin,  
    [in]  LPCWSTR  szAssemblyName,  
    [in]  LPCWSTR  szModuleName,  
    [out] LPCWSTR  szName,  
    [in]  ULONG    cchName,  
    [out] ULONG    *pcName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee0b7-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ee0b7-106">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="ee0b7-107">[in]使用されません。</span><span class="sxs-lookup"><span data-stu-id="ee0b7-107">[in] Not used.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="ee0b7-108">[in]使用されません。</span><span class="sxs-lookup"><span data-stu-id="ee0b7-108">[in] Not used.</span></span>  
  
 `szGlobalBin`  
 <span data-ttu-id="ee0b7-109">[in]使用されません。</span><span class="sxs-lookup"><span data-stu-id="ee0b7-109">[in] Not used.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="ee0b7-110">[in]モジュールの名前。</span><span class="sxs-lookup"><span data-stu-id="ee0b7-110">[in] The name of the module.</span></span>  
  
 `szModuleName`  
 <span data-ttu-id="ee0b7-111">[in]検索するアセンブリ。</span><span class="sxs-lookup"><span data-stu-id="ee0b7-111">[in] The assembly to be found.</span></span>  
  
 `szName`  
 <span data-ttu-id="ee0b7-112">[out]アセンブリの簡易名。</span><span class="sxs-lookup"><span data-stu-id="ee0b7-112">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="ee0b7-113">[in]サイズ (バイト単位) の`szName`します。</span><span class="sxs-lookup"><span data-stu-id="ee0b7-113">[in] The size, in bytes, of `szName`.</span></span>  
  
 `pcName`  
 <span data-ttu-id="ee0b7-114">[out]実際に返される文字数`szName`します。</span><span class="sxs-lookup"><span data-stu-id="ee0b7-114">[out] The number of characters actually returned in `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee0b7-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="ee0b7-115">Requirements</span></span>  
 <span data-ttu-id="ee0b7-116">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee0b7-116">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee0b7-117">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ee0b7-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ee0b7-118">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="ee0b7-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ee0b7-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee0b7-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee0b7-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="ee0b7-120">See also</span></span>

- [<span data-ttu-id="ee0b7-121">IMetaDataDispenserEx インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ee0b7-121">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="ee0b7-122">IMetaDataDispenser インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ee0b7-122">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
