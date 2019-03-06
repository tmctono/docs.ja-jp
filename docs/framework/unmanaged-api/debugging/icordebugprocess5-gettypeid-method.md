---
title: ICorDebugProcess5::GetTypeID メソッド
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugProcess5.GetTypeID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeID
helpviewer_keywords:
- ICorDebugProcess5::GetTypeID method [.NET Framework debugging]
- GetTypeID method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 47dbaea4-8857-462e-93ba-fff880fc9e50
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f58e4213959ca1cd6e65bc809a9ad964bebc31ae
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494793"
---
# <a name="icordebugprocess5gettypeid-method"></a><span data-ttu-id="329ce-102">ICorDebugProcess5::GetTypeID メソッド</span><span class="sxs-lookup"><span data-stu-id="329ce-102">ICorDebugProcess5::GetTypeID Method</span></span>
<span data-ttu-id="329ce-103">変換するオブジェクトのアドレスを[COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)識別子。</span><span class="sxs-lookup"><span data-stu-id="329ce-103">Converts an object address to a [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="329ce-104">構文</span><span class="sxs-lookup"><span data-stu-id="329ce-104">Syntax</span></span>  
  
```cpp
HRESULT GetTypeID(  
    [in] CORDB_ADDRESS obj,  
    [out] COR_TYPEID *pId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="329ce-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="329ce-105">Parameters</span></span>  
 `obj`  
 <span data-ttu-id="329ce-106">[in]オブジェクトのアドレス。</span><span class="sxs-lookup"><span data-stu-id="329ce-106">[in] The object address.</span></span>  
  
 `pId`  
 <span data-ttu-id="329ce-107">ポインター、 [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)オブジェクトを識別する値。</span><span class="sxs-lookup"><span data-stu-id="329ce-107">A pointer to the [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) value that identifies the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="329ce-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="329ce-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="329ce-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="329ce-109">Requirements</span></span>  
 <span data-ttu-id="329ce-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="329ce-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="329ce-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="329ce-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="329ce-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="329ce-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="329ce-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="329ce-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="329ce-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="329ce-114">See also</span></span>
- [<span data-ttu-id="329ce-115">ICorDebugProcess5 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="329ce-115">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="329ce-116">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="329ce-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
