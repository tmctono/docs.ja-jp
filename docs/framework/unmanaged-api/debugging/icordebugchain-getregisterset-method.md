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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 89237c20cbb145d14b7afbda8c00eb14b441d0d4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745281"
---
# <a name="icordebugchaingetregisterset-method"></a><span data-ttu-id="c9bf4-102">ICorDebugChain::GetRegisterSet メソッド</span><span class="sxs-lookup"><span data-stu-id="c9bf4-102">ICorDebugChain::GetRegisterSet Method</span></span>
<span data-ttu-id="c9bf4-103">このチェーンのアクティブな部分のレジスタ セットを取得します。</span><span class="sxs-lookup"><span data-stu-id="c9bf4-103">Gets the register set for the active part of this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9bf4-104">構文</span><span class="sxs-lookup"><span data-stu-id="c9bf4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c9bf4-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c9bf4-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="c9bf4-106">[out]アドレスへのポインター、 [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)このチェーンのアクティブな部分のレジスタを表すオブジェクトを設定します。</span><span class="sxs-lookup"><span data-stu-id="c9bf4-106">[out] A pointer to the address of an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) object that represents the register set for the active part of this chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9bf4-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="c9bf4-107">Requirements</span></span>  
 <span data-ttu-id="c9bf4-108">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9bf4-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9bf4-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c9bf4-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c9bf4-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c9bf4-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c9bf4-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9bf4-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
