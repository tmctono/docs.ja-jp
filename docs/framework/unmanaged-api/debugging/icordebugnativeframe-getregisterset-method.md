---
title: ICorDebugNativeFrame::GetRegisterSet メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetRegisterSet
helpviewer_keywords:
- ICorDebugNativeFrame::GetRegisterSet method [.NET Framework debugging]
- GetRegisterSet method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 6f309b5f-5556-4f1e-b1dd-4fe97fc81d01
topic_type:
- apiref
ms.openlocfilehash: ac7601f89c125cecbfbd212118420a800f495742
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73096807"
---
# <a name="icordebugnativeframegetregisterset-method"></a><span data-ttu-id="d0d99-102">ICorDebugNativeFrame::GetRegisterSet メソッド</span><span class="sxs-lookup"><span data-stu-id="d0d99-102">ICorDebugNativeFrame::GetRegisterSet Method</span></span>
<span data-ttu-id="d0d99-103">このスタックフレームのレジスタセットを取得します。</span><span class="sxs-lookup"><span data-stu-id="d0d99-103">Gets the register set for this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0d99-104">構文</span><span class="sxs-lookup"><span data-stu-id="d0d99-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d0d99-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d0d99-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="d0d99-106">入出力このスタックフレームの[レジスタセットを表す、オブジェクトの](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)アドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d0d99-106">[out] A pointer to the address of an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) object that represents the register set for this stack frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0d99-107">［要件］</span><span class="sxs-lookup"><span data-stu-id="d0d99-107">Requirements</span></span>  
 <span data-ttu-id="d0d99-108">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0d99-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0d99-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d0d99-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d0d99-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d0d99-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d0d99-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0d99-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0d99-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="d0d99-112">See also</span></span>
