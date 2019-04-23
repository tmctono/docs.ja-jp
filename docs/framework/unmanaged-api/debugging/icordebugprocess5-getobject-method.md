---
title: ICorDebugProcess5::GetObject メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetObject
helpviewer_keywords:
- GetObject method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetObject method [.NET Framework debugging]
ms.assetid: c8111502-5a20-447f-9dc2-76e8acd7ed5a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 35fdcd4bc3c9dbf6408f501256ce0df0174f9374
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59135656"
---
# <a name="icordebugprocess5getobject-method"></a><span data-ttu-id="18812-102">ICorDebugProcess5::GetObject メソッド</span><span class="sxs-lookup"><span data-stu-id="18812-102">ICorDebugProcess5::GetObject Method</span></span>
<span data-ttu-id="18812-103">オブジェクトのアドレスを"ICorDebugObjectValue"オブジェクトに変換します。</span><span class="sxs-lookup"><span data-stu-id="18812-103">Converts an object address to an "ICorDebugObjectValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18812-104">構文</span><span class="sxs-lookup"><span data-stu-id="18812-104">Syntax</span></span>  
  
```  
HRESULT GetObject(  
    [in] CORDB_ADDRESS addr,   
    [out] ICorDebugObjectValue **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="18812-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="18812-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="18812-106">[in]オブジェクトのアドレス。</span><span class="sxs-lookup"><span data-stu-id="18812-106">[in] The object address.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="18812-107">[out]"ICorDebugObjectValue"オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="18812-107">[out] A pointer to the address of an  "ICorDebugObjectValue" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="18812-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="18812-108">Remarks</span></span>  
 <span data-ttu-id="18812-109">場合`addr`が有効なマネージ オブジェクトを指していない、`GetObject`メソッドを返します。`E_FAIL`します。</span><span class="sxs-lookup"><span data-stu-id="18812-109">If `addr` does not point to a valid managed object, the `GetObject` method returns `E_FAIL`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18812-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="18812-110">Requirements</span></span>  
 <span data-ttu-id="18812-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="18812-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18812-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="18812-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="18812-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="18812-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="18812-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18812-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18812-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="18812-115">See also</span></span>

- [<span data-ttu-id="18812-116">ICorDebugProcess5 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="18812-116">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="18812-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="18812-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
