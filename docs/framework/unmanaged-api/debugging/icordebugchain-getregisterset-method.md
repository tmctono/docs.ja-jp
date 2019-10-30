---
title: ICorDebugChain::GetRegisterSet メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetRegisterSet
helpviewer_keywords:
- ICorDebugChain::GetRegisterSet method [.NET Framework debugging]
- GetRegisterSet method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: bc4288b6-3331-4ae3-990d-e1d6e62ecb67
topic_type:
- apiref
ms.openlocfilehash: d6ee36ac4d4510637e5f8240c3b8930a9bec7970
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123829"
---
# <a name="icordebugchaingetregisterset-method"></a><span data-ttu-id="74107-102">ICorDebugChain::GetRegisterSet メソッド</span><span class="sxs-lookup"><span data-stu-id="74107-102">ICorDebugChain::GetRegisterSet Method</span></span>
<span data-ttu-id="74107-103">このチェーンのアクティブな部分のレジスタセットを取得します。</span><span class="sxs-lookup"><span data-stu-id="74107-103">Gets the register set for the active part of this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74107-104">構文</span><span class="sxs-lookup"><span data-stu-id="74107-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="74107-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="74107-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="74107-106">入出力このチェーンのアクティブな部分のレジスタセットを表す、[のオブジェクトの](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)アドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="74107-106">[out] A pointer to the address of an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) object that represents the register set for the active part of this chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74107-107">［要件］</span><span class="sxs-lookup"><span data-stu-id="74107-107">Requirements</span></span>  
 <span data-ttu-id="74107-108">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74107-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74107-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="74107-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="74107-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="74107-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="74107-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74107-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
