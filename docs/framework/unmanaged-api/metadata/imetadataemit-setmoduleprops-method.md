---
title: IMetaDataEmit::SetModuleProps メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetModuleProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetModuleProps
helpviewer_keywords:
- SetModuleProps method [.NET Framework metadata]
- IMetaDataEmit::SetModuleProps method [.NET Framework metadata]
ms.assetid: b74d7629-5f46-458f-8d67-2456a1e7030c
topic_type:
- apiref
ms.openlocfilehash: 2d3c820975488fa722e7af6070611ba7e9686ce8
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445446"
---
# <a name="imetadataemitsetmoduleprops-method"></a><span data-ttu-id="2dbf8-102">IMetaDataEmit::SetModuleProps メソッド</span><span class="sxs-lookup"><span data-stu-id="2dbf8-102">IMetaDataEmit::SetModuleProps Method</span></span>
<span data-ttu-id="2dbf8-103">Updates references to a module defined by a prior call to [IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md).</span><span class="sxs-lookup"><span data-stu-id="2dbf8-103">Updates references to a module defined by a prior call to [IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2dbf8-104">構文</span><span class="sxs-lookup"><span data-stu-id="2dbf8-104">Syntax</span></span>  
  
```cpp  
HRESULT SetModuleProps (   
    [in]  LPCWSTR     szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2dbf8-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2dbf8-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="2dbf8-106">[in] The module name in Unicode.</span><span class="sxs-lookup"><span data-stu-id="2dbf8-106">[in] The module name in Unicode.</span></span> <span data-ttu-id="2dbf8-107">This is the file name only and not the full path name.</span><span class="sxs-lookup"><span data-stu-id="2dbf8-107">This is the file name only and not the full path name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2dbf8-108">［要件］</span><span class="sxs-lookup"><span data-stu-id="2dbf8-108">Requirements</span></span>  
 <span data-ttu-id="2dbf8-109">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dbf8-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2dbf8-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2dbf8-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2dbf8-111">**Library:** Used as a resource in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2dbf8-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2dbf8-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2dbf8-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dbf8-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="2dbf8-113">See also</span></span>

- [<span data-ttu-id="2dbf8-114">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2dbf8-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="2dbf8-115">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2dbf8-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
