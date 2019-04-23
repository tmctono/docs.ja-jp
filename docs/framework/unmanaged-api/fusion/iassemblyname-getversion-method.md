---
title: IAssemblyName::GetVersion メソッド
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetVersion
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetVersion
helpviewer_keywords:
- IAssemblyName::GetVersion method [.NET Framework fusion]
- GetVersion method, IAssemblyName interface [.NET Framework fusion]
ms.assetid: 42230928-2c33-41fd-9519-d96efef6c7af
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a28cb9f1fd2e12cd750d4eeb8db6c2d7a181b414
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59197426"
---
# <a name="iassemblynamegetversion-method"></a><span data-ttu-id="d9c19-102">IAssemblyName::GetVersion メソッド</span><span class="sxs-lookup"><span data-stu-id="d9c19-102">IAssemblyName::GetVersion Method</span></span>
<span data-ttu-id="d9c19-103">これによって参照されるアセンブリのバージョン情報を取得[IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="d9c19-103">Gets the version information for the assembly referenced by this [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9c19-104">構文</span><span class="sxs-lookup"><span data-stu-id="d9c19-104">Syntax</span></span>  
  
```  
HRESULT GetVersion (  
    [out] LPDWORD pdwVersionHi,  
    [out] LPDWORD pdwVersionLow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9c19-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d9c19-105">Parameters</span></span>  
 `pdwVersionHi`  
 <span data-ttu-id="d9c19-106">[out]バージョンの上位 32 ビット。</span><span class="sxs-lookup"><span data-stu-id="d9c19-106">[out] The high 32 bits of the version.</span></span>  
  
 `pdwVersionLow`  
 <span data-ttu-id="d9c19-107">[out]バージョンの下位 32 ビット。</span><span class="sxs-lookup"><span data-stu-id="d9c19-107">[out] The low 32 bits of the version.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9c19-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="d9c19-108">Requirements</span></span>  
 <span data-ttu-id="d9c19-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9c19-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9c19-110">**ヘッダー:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="d9c19-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="d9c19-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9c19-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9c19-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="d9c19-112">See also</span></span>

- [<span data-ttu-id="d9c19-113">IAssemblyName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d9c19-113">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
