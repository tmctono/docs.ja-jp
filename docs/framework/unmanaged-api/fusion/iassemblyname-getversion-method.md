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
ms.openlocfilehash: c0a43dc1640bdaa0ae104832eb4d1f8eb15b0392
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134330"
---
# <a name="iassemblynamegetversion-method"></a><span data-ttu-id="92d90-102">IAssemblyName::GetVersion メソッド</span><span class="sxs-lookup"><span data-stu-id="92d90-102">IAssemblyName::GetVersion Method</span></span>
<span data-ttu-id="92d90-103">この[IAssemblyName](iassemblyname-interface.md)オブジェクトによって参照されるアセンブリのバージョン情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="92d90-103">Gets the version information for the assembly referenced by this [IAssemblyName](iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92d90-104">構文</span><span class="sxs-lookup"><span data-stu-id="92d90-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVersion (  
    [out] LPDWORD pdwVersionHi,  
    [out] LPDWORD pdwVersionLow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="92d90-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="92d90-105">Parameters</span></span>  
 `pdwVersionHi`  
 <span data-ttu-id="92d90-106">入出力バージョンの上位32ビット。</span><span class="sxs-lookup"><span data-stu-id="92d90-106">[out] The high 32 bits of the version.</span></span>  
  
 `pdwVersionLow`  
 <span data-ttu-id="92d90-107">入出力バージョンの下位32ビット。</span><span class="sxs-lookup"><span data-stu-id="92d90-107">[out] The low 32 bits of the version.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92d90-108">［要件］</span><span class="sxs-lookup"><span data-stu-id="92d90-108">Requirements</span></span>  
 <span data-ttu-id="92d90-109">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92d90-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92d90-110">**ヘッダー:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="92d90-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="92d90-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92d90-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92d90-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="92d90-112">See also</span></span>

- [<span data-ttu-id="92d90-113">IAssemblyName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="92d90-113">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
