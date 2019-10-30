---
title: ICorDebugChain::GetReason メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- GetReason
helpviewer_keywords:
- GetReason method [.NET Framework debugging]
- ICorDebugChain::GetReason method [.NET Framework debugging]
ms.assetid: 9f9f62b9-113a-4a98-8f9b-b593cef27b03
topic_type:
- apiref
ms.openlocfilehash: e51ee2e4d44af547c82a21a782121976d07118c5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124713"
---
# <a name="icordebugchaingetreason-method"></a><span data-ttu-id="01157-102">ICorDebugChain::GetReason メソッド</span><span class="sxs-lookup"><span data-stu-id="01157-102">ICorDebugChain::GetReason Method</span></span>
<span data-ttu-id="01157-103">この呼び出しチェーンの genesis の理由を取得します。</span><span class="sxs-lookup"><span data-stu-id="01157-103">Gets the reason for the genesis of this calling chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01157-104">構文</span><span class="sxs-lookup"><span data-stu-id="01157-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReason (  
    [out] CorDebugChainReason *pReason  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="01157-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="01157-105">Parameters</span></span>  
 `pReason`  
 <span data-ttu-id="01157-106">入出力この呼び出しチェーンの genesis の理由を示す、CorDebugChainReason 列挙体の値 (ビットごとの組み合わせ) へのポインター。</span><span class="sxs-lookup"><span data-stu-id="01157-106">[out] A pointer to a value (a bitwise combination) of the CorDebugChainReason enumeration that indicates the reason for the genesis of this calling chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01157-107">［要件］</span><span class="sxs-lookup"><span data-stu-id="01157-107">Requirements</span></span>  
 <span data-ttu-id="01157-108">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01157-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01157-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="01157-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="01157-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="01157-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="01157-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01157-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
