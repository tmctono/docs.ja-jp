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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0e5120b5fddf621d6f4c684c4c432fda4f5c0117
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745260"
---
# <a name="icordebugchaingetreason-method"></a><span data-ttu-id="5c440-102">ICorDebugChain::GetReason メソッド</span><span class="sxs-lookup"><span data-stu-id="5c440-102">ICorDebugChain::GetReason Method</span></span>
<span data-ttu-id="5c440-103">この呼び出しチェーンの起源の理由を取得します。</span><span class="sxs-lookup"><span data-stu-id="5c440-103">Gets the reason for the genesis of this calling chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c440-104">構文</span><span class="sxs-lookup"><span data-stu-id="5c440-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReason (  
    [out] CorDebugChainReason *pReason  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c440-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5c440-105">Parameters</span></span>  
 `pReason`  
 <span data-ttu-id="5c440-106">[out]この呼び出しチェーンの起源の理由を示す CorDebugChainReason 列挙型の値 (ビットごとの組み合わせ) へのポインター。</span><span class="sxs-lookup"><span data-stu-id="5c440-106">[out] A pointer to a value (a bitwise combination) of the CorDebugChainReason enumeration that indicates the reason for the genesis of this calling chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c440-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="5c440-107">Requirements</span></span>  
 <span data-ttu-id="5c440-108">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c440-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c440-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5c440-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5c440-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5c440-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5c440-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c440-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
