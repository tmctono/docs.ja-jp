---
title: ICorDebugEnum::Clone メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugEnum.Clone
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum::Clone
helpviewer_keywords:
- Clone method, ICorDebugEnum interface [.NET Framework debugging]
- ICorDebugEnum::Clone method [.NET Framework debugging]
ms.assetid: 57eefaf3-75cf-4496-bc94-88c0706861b7
topic_type:
- apiref
ms.openlocfilehash: 2ec769c343ad055132c6d84e64600fc459357a85
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124704"
---
# <a name="icordebugenumclone-method"></a><span data-ttu-id="35b50-102">ICorDebugEnum::Clone メソッド</span><span class="sxs-lookup"><span data-stu-id="35b50-102">ICorDebugEnum::Clone Method</span></span>
<span data-ttu-id="35b50-103">この ICorDebugEnum オブジェクトのコピーを作成します。</span><span class="sxs-lookup"><span data-stu-id="35b50-103">Creates a copy of this ICorDebugEnum object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35b50-104">構文</span><span class="sxs-lookup"><span data-stu-id="35b50-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone (  
    [out] ICorDebugEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35b50-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="35b50-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="35b50-106">入出力この `ICorDebugEnum` オブジェクトのコピーである `ICorDebugEnum` オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="35b50-106">[out] A pointer to the address of an `ICorDebugEnum` object that is a copy of this `ICorDebugEnum` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35b50-107">［要件］</span><span class="sxs-lookup"><span data-stu-id="35b50-107">Requirements</span></span>  
 <span data-ttu-id="35b50-108">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35b50-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35b50-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="35b50-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="35b50-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="35b50-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="35b50-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35b50-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
