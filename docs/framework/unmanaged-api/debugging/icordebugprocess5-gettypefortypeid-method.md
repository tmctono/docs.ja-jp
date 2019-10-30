---
title: ICorDebugProcess5::GetTypeForTypeID メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetTypeForTypeID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeForTypeID
helpviewer_keywords:
- GetTypeForTypeID method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetTypeForTypeID method [.NET Framework debugging]
ms.assetid: e0eed5a8-fa6d-4818-bd00-7babcea30325
topic_type:
- apiref
ms.openlocfilehash: 39f5c1813b08f4d72c610820b1434e29eb4aec8e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121269"
---
# <a name="icordebugprocess5gettypefortypeid-method"></a><span data-ttu-id="16365-102">ICorDebugProcess5::GetTypeForTypeID メソッド</span><span class="sxs-lookup"><span data-stu-id="16365-102">ICorDebugProcess5::GetTypeForTypeID Method</span></span>
<span data-ttu-id="16365-103">型識別子をの型の値に変換します。</span><span class="sxs-lookup"><span data-stu-id="16365-103">Converts a type identifier to an ICorDebugType value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16365-104">構文</span><span class="sxs-lookup"><span data-stu-id="16365-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeForTypeID(  
    [in] COR_TYPEID id, [  
    out] ICorDebugType **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="16365-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="16365-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="16365-106">から型識別子。</span><span class="sxs-lookup"><span data-stu-id="16365-106">[in] The type identifier.</span></span>  
  
 `ppType`  
 <span data-ttu-id="16365-107">入出力テキストオブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="16365-107">[out] A pointer to the address of an ICorDebugType object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="16365-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="16365-108">Remarks</span></span>  
 <span data-ttu-id="16365-109">場合によっては、型識別子を返すメソッドが null `COR_TYPEID` 値を返すことがあります。</span><span class="sxs-lookup"><span data-stu-id="16365-109">In some cases, methods that return a type identifier may return a null `COR_TYPEID` value.</span></span> <span data-ttu-id="16365-110">この値が `id` 引数として渡された場合、`GetTypeForTypeID` メソッドは失敗し、`E_FAIL`が返されます。</span><span class="sxs-lookup"><span data-stu-id="16365-110">If this value is passed as the `id` argument, the `GetTypeForTypeID` method will fail and return `E_FAIL`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16365-111">［要件］</span><span class="sxs-lookup"><span data-stu-id="16365-111">Requirements</span></span>  
 <span data-ttu-id="16365-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16365-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16365-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="16365-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="16365-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="16365-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="16365-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16365-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16365-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="16365-116">See also</span></span>

- [<span data-ttu-id="16365-117">ICorDebugProcess5 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="16365-117">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="16365-118">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="16365-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
