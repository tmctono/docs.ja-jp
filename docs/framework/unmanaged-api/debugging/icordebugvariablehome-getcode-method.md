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
ms.openlocfilehash: 6c9b334535f8f6652f30a4b5c9de64bde435c3bd
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496223"
---
# <a name="icordebugvariablehomegetcode-method"></a><span data-ttu-id="874d9-102">ICorDebugVariableHome::GetCode メソッド</span><span class="sxs-lookup"><span data-stu-id="874d9-102">ICorDebugVariableHome::GetCode Method</span></span>
<span data-ttu-id="874d9-103">これを含む"ICorDebugCode"インスタンスを取得します。 [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="874d9-103">Gets the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="874d9-104">構文</span><span class="sxs-lookup"><span data-stu-id="874d9-104">Syntax</span></span>  
  
```  
HRESULT GetCode(  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="874d9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="874d9-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="874d9-106">[out]これを含む"ICorDebugCode"インスタンスのアドレスへのポインター [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="874d9-106">[out] A pointer to the address of the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="874d9-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="874d9-107">Requirements</span></span>  
 <span data-ttu-id="874d9-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="874d9-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="874d9-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="874d9-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="874d9-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="874d9-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="874d9-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="874d9-111">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="874d9-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="874d9-112">See also</span></span>
- [<span data-ttu-id="874d9-113">ICorDebugVariableHome インターフェイス</span><span class="sxs-lookup"><span data-stu-id="874d9-113">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)

