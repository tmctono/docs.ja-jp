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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c5ddc2646b560814adef01f2508f3792abe13c1d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744526"
---
# <a name="iassemblynamegetproperty-method"></a><span data-ttu-id="e629a-102">IAssemblyName::GetProperty メソッド</span><span class="sxs-lookup"><span data-stu-id="e629a-102">IAssemblyName::GetProperty Method</span></span>
<span data-ttu-id="e629a-103">指定したプロパティの識別子によって参照されるプロパティにポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="e629a-103">Gets a pointer to the property referenced by the specified property identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e629a-104">構文</span><span class="sxs-lookup"><span data-stu-id="e629a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProperty (  
    [in]      DWORD    PropertyId,  
    [out]     LPVOID   pvProperty,  
    [in, out] LPDWORD  pcbProperty  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e629a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e629a-105">Parameters</span></span>  
 `PropertyId`  
 <span data-ttu-id="e629a-106">[in]要求されたプロパティの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="e629a-106">[in] The unique identifier for the requested property.</span></span>  
  
 `pvProperty`  
 <span data-ttu-id="e629a-107">[out]返されたプロパティのデータ。</span><span class="sxs-lookup"><span data-stu-id="e629a-107">[out] The returned property data.</span></span>  
  
 `pcbProperty`  
 <span data-ttu-id="e629a-108">[入力、出力]サイズ (バイト単位) の`pvProperty`します。</span><span class="sxs-lookup"><span data-stu-id="e629a-108">[in, out] The size, in bytes, of `pvProperty`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e629a-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="e629a-109">Requirements</span></span>  
 <span data-ttu-id="e629a-110">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e629a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e629a-111">**ヘッダー:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="e629a-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="e629a-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e629a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e629a-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="e629a-113">See also</span></span>

- [<span data-ttu-id="e629a-114">IAssemblyName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e629a-114">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
