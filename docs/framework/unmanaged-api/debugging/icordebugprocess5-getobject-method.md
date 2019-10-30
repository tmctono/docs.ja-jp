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
ms.openlocfilehash: e4d297023d96de83965c3d04ca9efe2613fd54d0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73084442"
---
# <a name="icordebugprocess5getobject-method"></a><span data-ttu-id="ef00a-102">ICorDebugProcess5::GetObject メソッド</span><span class="sxs-lookup"><span data-stu-id="ef00a-102">ICorDebugProcess5::GetObject Method</span></span>
<span data-ttu-id="ef00a-103">オブジェクトのアドレスを "の値" オブジェクトに変換します。</span><span class="sxs-lookup"><span data-stu-id="ef00a-103">Converts an object address to an "ICorDebugObjectValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef00a-104">構文</span><span class="sxs-lookup"><span data-stu-id="ef00a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObject(  
    [in] CORDB_ADDRESS addr,   
    [out] ICorDebugObjectValue **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef00a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ef00a-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="ef00a-106">からオブジェクトのアドレス。</span><span class="sxs-lookup"><span data-stu-id="ef00a-106">[in] The object address.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="ef00a-107">入出力"の値" オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="ef00a-107">[out] A pointer to the address of an  "ICorDebugObjectValue" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef00a-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="ef00a-108">Remarks</span></span>  
 <span data-ttu-id="ef00a-109">`addr` が有効なマネージオブジェクトを指していない場合、`GetObject` メソッドは `E_FAIL`を返します。</span><span class="sxs-lookup"><span data-stu-id="ef00a-109">If `addr` does not point to a valid managed object, the `GetObject` method returns `E_FAIL`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef00a-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="ef00a-110">Requirements</span></span>  
 <span data-ttu-id="ef00a-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef00a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef00a-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ef00a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ef00a-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ef00a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ef00a-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef00a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef00a-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="ef00a-115">See also</span></span>

- [<span data-ttu-id="ef00a-116">ICorDebugProcess5 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ef00a-116">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="ef00a-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ef00a-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
