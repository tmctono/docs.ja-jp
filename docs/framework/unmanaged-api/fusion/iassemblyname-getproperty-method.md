---
title: IAssemblyName::GetProperty メソッド
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetProperty
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetProperty
helpviewer_keywords:
- IAssemblyName::GetProperty method [.NET Framework fusion]
- GetProperty method [.NET Framework fusion]
ms.assetid: e59fda62-77d5-4e37-89cb-ce7ae4627975
topic_type:
- apiref
ms.openlocfilehash: b86828e01fb00b12feff2ed451793c240e16e240
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134389"
---
# <a name="iassemblynamegetproperty-method"></a><span data-ttu-id="6fd3a-102">IAssemblyName::GetProperty メソッド</span><span class="sxs-lookup"><span data-stu-id="6fd3a-102">IAssemblyName::GetProperty Method</span></span>
<span data-ttu-id="6fd3a-103">指定したプロパティ識別子によって参照されるプロパティへのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="6fd3a-103">Gets a pointer to the property referenced by the specified property identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fd3a-104">構文</span><span class="sxs-lookup"><span data-stu-id="6fd3a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProperty (  
    [in]      DWORD    PropertyId,  
    [out]     LPVOID   pvProperty,  
    [in, out] LPDWORD  pcbProperty  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6fd3a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6fd3a-105">Parameters</span></span>  
 `PropertyId`  
 <span data-ttu-id="6fd3a-106">から要求されたプロパティの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="6fd3a-106">[in] The unique identifier for the requested property.</span></span>  
  
 `pvProperty`  
 <span data-ttu-id="6fd3a-107">入出力返されたプロパティデータ。</span><span class="sxs-lookup"><span data-stu-id="6fd3a-107">[out] The returned property data.</span></span>  
  
 `pcbProperty`  
 <span data-ttu-id="6fd3a-108">[入力、出力]`pvProperty`のサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="6fd3a-108">[in, out] The size, in bytes, of `pvProperty`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6fd3a-109">［要件］</span><span class="sxs-lookup"><span data-stu-id="6fd3a-109">Requirements</span></span>  
 <span data-ttu-id="6fd3a-110">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fd3a-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fd3a-111">**ヘッダー:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="6fd3a-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="6fd3a-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6fd3a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fd3a-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="6fd3a-113">See also</span></span>

- [<span data-ttu-id="6fd3a-114">IAssemblyName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6fd3a-114">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
