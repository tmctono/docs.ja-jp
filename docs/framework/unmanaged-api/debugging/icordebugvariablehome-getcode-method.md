---
title: ICorDebugVariableHome::GetCode メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetCode
helpviewer_keywords:
- ICorDebugVariableHome::GetCode method [.NET Framework debugging]
- GetCode method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: ef002890-4a7b-4a5d-abbf-16c60083f794
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4c0cae29cceb3f23c7d09cf096937c99641d5a87
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67773591"
---
# <a name="icordebugvariablehomegetcode-method"></a><span data-ttu-id="6cdd1-102">ICorDebugVariableHome::GetCode メソッド</span><span class="sxs-lookup"><span data-stu-id="6cdd1-102">ICorDebugVariableHome::GetCode Method</span></span>
<span data-ttu-id="6cdd1-103">これを含む"ICorDebugCode"インスタンスを取得します。 [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="6cdd1-103">Gets the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6cdd1-104">構文</span><span class="sxs-lookup"><span data-stu-id="6cdd1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCode(  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6cdd1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6cdd1-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="6cdd1-106">[out]これを含む"ICorDebugCode"インスタンスのアドレスへのポインター [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="6cdd1-106">[out] A pointer to the address of the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6cdd1-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="6cdd1-107">Requirements</span></span>  
 <span data-ttu-id="6cdd1-108">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6cdd1-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6cdd1-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6cdd1-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6cdd1-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6cdd1-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6cdd1-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6cdd1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cdd1-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="6cdd1-112">See also</span></span>

- [<span data-ttu-id="6cdd1-113">ICorDebugVariableHome インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6cdd1-113">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
