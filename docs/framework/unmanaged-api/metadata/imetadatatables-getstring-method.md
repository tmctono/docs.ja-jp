---
title: IMetaDataTables::GetString メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetString
helpviewer_keywords:
- IMetaDataTables::GetString method [.NET Framework metadata]
- GetString method, IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 895c35cf-b95d-4e3b-93b5-cfc1cf9044fc
topic_type:
- apiref
ms.openlocfilehash: 055499230f500cb7249746e1acbf46b4548d25bc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426798"
---
# <a name="imetadatatablesgetstring-method"></a><span data-ttu-id="aacb6-102">IMetaDataTables::GetString メソッド</span><span class="sxs-lookup"><span data-stu-id="aacb6-102">IMetaDataTables::GetString Method</span></span>
<span data-ttu-id="aacb6-103">Gets the string at the specified index from the table column in the current reference scope.</span><span class="sxs-lookup"><span data-stu-id="aacb6-103">Gets the string at the specified index from the table column in the current reference scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aacb6-104">構文</span><span class="sxs-lookup"><span data-stu-id="aacb6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetString (   
    [in]  ULONG       ixString,  
    [out] const char  **ppString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aacb6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="aacb6-105">Parameters</span></span>  
 `ixString`  
 <span data-ttu-id="aacb6-106">[in] The index at which to start to search for the next value.</span><span class="sxs-lookup"><span data-stu-id="aacb6-106">[in] The index at which to start to search for the next value.</span></span>  
  
 `ppString`  
 <span data-ttu-id="aacb6-107">[out] A pointer to a pointer to the returned string value.</span><span class="sxs-lookup"><span data-stu-id="aacb6-107">[out] A pointer to a pointer to the returned string value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aacb6-108">［要件］</span><span class="sxs-lookup"><span data-stu-id="aacb6-108">Requirements</span></span>  
 <span data-ttu-id="aacb6-109">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aacb6-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aacb6-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="aacb6-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="aacb6-111">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="aacb6-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="aacb6-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aacb6-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aacb6-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="aacb6-113">See also</span></span>

- [<span data-ttu-id="aacb6-114">IMetaDataTables インターフェイス</span><span class="sxs-lookup"><span data-stu-id="aacb6-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="aacb6-115">IMetaDataTables2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="aacb6-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
