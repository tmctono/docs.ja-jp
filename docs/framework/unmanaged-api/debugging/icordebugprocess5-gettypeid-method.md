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
ms.openlocfilehash: 499e1fd859a66bb6992c6d02a46e38c514503bd8
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205584"
---
# <a name="icordebugprocess5gettypeid-method"></a><span data-ttu-id="00c7d-102">ICorDebugProcess5::GetTypeID メソッド</span><span class="sxs-lookup"><span data-stu-id="00c7d-102">ICorDebugProcess5::GetTypeID Method</span></span>
<span data-ttu-id="00c7d-103">オブジェクトのアドレスを[COR_TYPEID](cor-typeid-structure.md)識別子に変換します。</span><span class="sxs-lookup"><span data-stu-id="00c7d-103">Converts an object address to a [COR_TYPEID](cor-typeid-structure.md) identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00c7d-104">構文</span><span class="sxs-lookup"><span data-stu-id="00c7d-104">Syntax</span></span>  
  
```cpp
HRESULT GetTypeID(  
    [in] CORDB_ADDRESS obj,  
    [out] COR_TYPEID *pId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="00c7d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="00c7d-105">Parameters</span></span>  
 `obj`  
 <span data-ttu-id="00c7d-106">からオブジェクトのアドレス。</span><span class="sxs-lookup"><span data-stu-id="00c7d-106">[in] The object address.</span></span>  
  
 `pId`  
 <span data-ttu-id="00c7d-107">オブジェクトを識別する[COR_TYPEID](cor-typeid-structure.md)値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="00c7d-107">A pointer to the [COR_TYPEID](cor-typeid-structure.md) value that identifies the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="00c7d-108">解説</span><span class="sxs-lookup"><span data-stu-id="00c7d-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00c7d-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="00c7d-109">Requirements</span></span>  
 <span data-ttu-id="00c7d-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00c7d-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00c7d-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="00c7d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="00c7d-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="00c7d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="00c7d-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00c7d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00c7d-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="00c7d-114">See also</span></span>

- [<span data-ttu-id="00c7d-115">ICorDebugProcess5 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="00c7d-115">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="00c7d-116">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="00c7d-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
