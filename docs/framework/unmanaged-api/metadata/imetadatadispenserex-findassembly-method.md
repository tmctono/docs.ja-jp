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
ms.openlocfilehash: 50aebb09924b93a622e5b7d84e65e41ee91f6018
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006195"
---
# <a name="imetadatadispenserexfindassembly-method"></a><span data-ttu-id="1507a-102">IMetaDataDispenserEx::FindAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="1507a-102">IMetaDataDispenserEx::FindAssembly Method</span></span>
<span data-ttu-id="1507a-103">このメソッドは実装されていません。</span><span class="sxs-lookup"><span data-stu-id="1507a-103">This method is not implemented.</span></span> <span data-ttu-id="1507a-104">呼び出された場合は E_NOTIMPL を返します。</span><span class="sxs-lookup"><span data-stu-id="1507a-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1507a-105">構文</span><span class="sxs-lookup"><span data-stu-id="1507a-105">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="1507a-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1507a-106">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="1507a-107">から使用しません。</span><span class="sxs-lookup"><span data-stu-id="1507a-107">[in] Not used.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="1507a-108">から使用しません。</span><span class="sxs-lookup"><span data-stu-id="1507a-108">[in] Not used.</span></span>  
  
 `szGlobalBin`  
 <span data-ttu-id="1507a-109">から使用しません。</span><span class="sxs-lookup"><span data-stu-id="1507a-109">[in] Not used.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="1507a-110">から検索するアセンブリ。</span><span class="sxs-lookup"><span data-stu-id="1507a-110">[in] The assembly to be found.</span></span>  
  
 `szName`  
 <span data-ttu-id="1507a-111">入出力アセンブリの簡易名。</span><span class="sxs-lookup"><span data-stu-id="1507a-111">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="1507a-112">からのサイズ (バイト単位) `szName` 。</span><span class="sxs-lookup"><span data-stu-id="1507a-112">[in] The size, in bytes, of `szName`.</span></span>  
  
 `pcName`  
 <span data-ttu-id="1507a-113">入出力で実際に返された文字数 `szName` 。</span><span class="sxs-lookup"><span data-stu-id="1507a-113">[out] The number of characters actually returned in `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1507a-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="1507a-114">Requirements</span></span>  
 <span data-ttu-id="1507a-115">**プラットフォーム:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1507a-115">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1507a-116">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="1507a-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1507a-117">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="1507a-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1507a-118">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1507a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1507a-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="1507a-119">See also</span></span>

- [<span data-ttu-id="1507a-120">IMetaDataDispenserEx インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1507a-120">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="1507a-121">IMetaDataDispenser インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1507a-121">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
