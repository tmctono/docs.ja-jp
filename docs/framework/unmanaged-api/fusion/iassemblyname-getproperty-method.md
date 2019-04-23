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
ms.openlocfilehash: 9af0773c2ef066c103f823e4d28c0fd6e9eadc24
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59086560"
---
# <a name="iassemblynamegetproperty-method"></a><span data-ttu-id="99506-102">IAssemblyName::GetProperty メソッド</span><span class="sxs-lookup"><span data-stu-id="99506-102">IAssemblyName::GetProperty Method</span></span>
<span data-ttu-id="99506-103">指定したプロパティの識別子によって参照されるプロパティにポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="99506-103">Gets a pointer to the property referenced by the specified property identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99506-104">構文</span><span class="sxs-lookup"><span data-stu-id="99506-104">Syntax</span></span>  
  
```  
HRESULT GetProperty (  
    [in]      DWORD    PropertyId,  
    [out]     LPVOID   pvProperty,  
    [in, out] LPDWORD  pcbProperty  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99506-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="99506-105">Parameters</span></span>  
 `PropertyId`  
 <span data-ttu-id="99506-106">[in]要求されたプロパティの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="99506-106">[in] The unique identifier for the requested property.</span></span>  
  
 `pvProperty`  
 <span data-ttu-id="99506-107">[out]返されたプロパティのデータ。</span><span class="sxs-lookup"><span data-stu-id="99506-107">[out] The returned property data.</span></span>  
  
 `pcbProperty`  
 <span data-ttu-id="99506-108">[入力、出力]サイズ (バイト単位) の`pvProperty`します。</span><span class="sxs-lookup"><span data-stu-id="99506-108">[in, out] The size, in bytes, of `pvProperty`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99506-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="99506-109">Requirements</span></span>  
 <span data-ttu-id="99506-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="99506-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99506-111">**ヘッダー:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="99506-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="99506-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99506-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99506-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="99506-113">See also</span></span>

- [<span data-ttu-id="99506-114">IAssemblyName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="99506-114">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
