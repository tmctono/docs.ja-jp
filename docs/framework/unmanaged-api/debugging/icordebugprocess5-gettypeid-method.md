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
ms.openlocfilehash: 6c159780b9019127d166e8437ea4ed214284011f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121264"
---
# <a name="icordebugprocess5gettypeid-method"></a><span data-ttu-id="6d64c-102">ICorDebugProcess5::GetTypeID メソッド</span><span class="sxs-lookup"><span data-stu-id="6d64c-102">ICorDebugProcess5::GetTypeID Method</span></span>
<span data-ttu-id="6d64c-103">オブジェクトのアドレスを[COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)識別子に変換します。</span><span class="sxs-lookup"><span data-stu-id="6d64c-103">Converts an object address to a [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d64c-104">構文</span><span class="sxs-lookup"><span data-stu-id="6d64c-104">Syntax</span></span>  
  
```cpp
HRESULT GetTypeID(  
    [in] CORDB_ADDRESS obj,  
    [out] COR_TYPEID *pId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d64c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6d64c-105">Parameters</span></span>  
 `obj`  
 <span data-ttu-id="6d64c-106">からオブジェクトのアドレス。</span><span class="sxs-lookup"><span data-stu-id="6d64c-106">[in] The object address.</span></span>  
  
 `pId`  
 <span data-ttu-id="6d64c-107">オブジェクトを識別する[COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="6d64c-107">A pointer to the [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) value that identifies the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6d64c-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="6d64c-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d64c-109">［要件］</span><span class="sxs-lookup"><span data-stu-id="6d64c-109">Requirements</span></span>  
 <span data-ttu-id="6d64c-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d64c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d64c-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6d64c-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6d64c-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d64c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d64c-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d64c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d64c-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="6d64c-114">See also</span></span>

- [<span data-ttu-id="6d64c-115">ICorDebugProcess5 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6d64c-115">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="6d64c-116">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6d64c-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
