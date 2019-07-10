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
ms.openlocfilehash: 2ec3dc37984228565b4a3fcc560d3857a1c1e46d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767332"
---
# <a name="icordebugprocess5getobject-method"></a><span data-ttu-id="c4123-102">ICorDebugProcess5::GetObject メソッド</span><span class="sxs-lookup"><span data-stu-id="c4123-102">ICorDebugProcess5::GetObject Method</span></span>
<span data-ttu-id="c4123-103">オブジェクトのアドレスを"ICorDebugObjectValue"オブジェクトに変換します。</span><span class="sxs-lookup"><span data-stu-id="c4123-103">Converts an object address to an "ICorDebugObjectValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4123-104">構文</span><span class="sxs-lookup"><span data-stu-id="c4123-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObject(  
    [in] CORDB_ADDRESS addr,   
    [out] ICorDebugObjectValue **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4123-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c4123-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="c4123-106">[in]オブジェクトのアドレス。</span><span class="sxs-lookup"><span data-stu-id="c4123-106">[in] The object address.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="c4123-107">[out]"ICorDebugObjectValue"オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="c4123-107">[out] A pointer to the address of an  "ICorDebugObjectValue" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4123-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="c4123-108">Remarks</span></span>  
 <span data-ttu-id="c4123-109">場合`addr`が有効なマネージ オブジェクトを指していない、`GetObject`メソッドを返します。`E_FAIL`します。</span><span class="sxs-lookup"><span data-stu-id="c4123-109">If `addr` does not point to a valid managed object, the `GetObject` method returns `E_FAIL`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4123-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="c4123-110">Requirements</span></span>  
 <span data-ttu-id="c4123-111">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4123-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4123-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c4123-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c4123-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4123-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c4123-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4123-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4123-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="c4123-115">See also</span></span>

- [<span data-ttu-id="c4123-116">ICorDebugProcess5 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c4123-116">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="c4123-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c4123-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
