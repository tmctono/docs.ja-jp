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
ms.openlocfilehash: e73c95d8c720ed3263d6a66c48bdb5b5582eb686
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442183"
---
# <a name="imetadatadispenserexfindassemblymodule-method"></a><span data-ttu-id="13c5d-102">IMetaDataDispenserEx::FindAssemblyModule メソッド</span><span class="sxs-lookup"><span data-stu-id="13c5d-102">IMetaDataDispenserEx::FindAssemblyModule Method</span></span>
<span data-ttu-id="13c5d-103">このメソッドは実装されていません。</span><span class="sxs-lookup"><span data-stu-id="13c5d-103">This method is not implemented.</span></span> <span data-ttu-id="13c5d-104">呼び出された場合は E_NOTIMPL を返します。</span><span class="sxs-lookup"><span data-stu-id="13c5d-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13c5d-105">構文</span><span class="sxs-lookup"><span data-stu-id="13c5d-105">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="13c5d-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="13c5d-106">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="13c5d-107">から使用しません。</span><span class="sxs-lookup"><span data-stu-id="13c5d-107">[in] Not used.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="13c5d-108">から使用しません。</span><span class="sxs-lookup"><span data-stu-id="13c5d-108">[in] Not used.</span></span>  
  
 `szGlobalBin`  
 <span data-ttu-id="13c5d-109">から使用しません。</span><span class="sxs-lookup"><span data-stu-id="13c5d-109">[in] Not used.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="13c5d-110">からモジュールの名前。</span><span class="sxs-lookup"><span data-stu-id="13c5d-110">[in] The name of the module.</span></span>  
  
 `szModuleName`  
 <span data-ttu-id="13c5d-111">から検索するアセンブリ。</span><span class="sxs-lookup"><span data-stu-id="13c5d-111">[in] The assembly to be found.</span></span>  
  
 `szName`  
 <span data-ttu-id="13c5d-112">入出力アセンブリの簡易名。</span><span class="sxs-lookup"><span data-stu-id="13c5d-112">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="13c5d-113">から`szName`のサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="13c5d-113">[in] The size, in bytes, of `szName`.</span></span>  
  
 `pcName`  
 <span data-ttu-id="13c5d-114">入出力`szName`に実際に返された文字数。</span><span class="sxs-lookup"><span data-stu-id="13c5d-114">[out] The number of characters actually returned in `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13c5d-115">要件</span><span class="sxs-lookup"><span data-stu-id="13c5d-115">Requirements</span></span>  
 <span data-ttu-id="13c5d-116">**プラットフォーム:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13c5d-116">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13c5d-117">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="13c5d-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="13c5d-118">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="13c5d-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="13c5d-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13c5d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13c5d-120">参照</span><span class="sxs-lookup"><span data-stu-id="13c5d-120">See also</span></span>

- [<span data-ttu-id="13c5d-121">IMetaDataDispenserEx インターフェイス</span><span class="sxs-lookup"><span data-stu-id="13c5d-121">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="13c5d-122">IMetaDataDispenser インターフェイス</span><span class="sxs-lookup"><span data-stu-id="13c5d-122">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
