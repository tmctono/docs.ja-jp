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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aeb4ad1dffe4553b243b5168037aea8b68f8244b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61930209"
---
# <a name="icordebugprocess5gettypefortypeid-method"></a><span data-ttu-id="63ce4-102">ICorDebugProcess5::GetTypeForTypeID メソッド</span><span class="sxs-lookup"><span data-stu-id="63ce4-102">ICorDebugProcess5::GetTypeForTypeID Method</span></span>
<span data-ttu-id="63ce4-103">ICorDebugType 値を型識別子に変換します。</span><span class="sxs-lookup"><span data-stu-id="63ce4-103">Converts a type identifier to an ICorDebugType value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63ce4-104">構文</span><span class="sxs-lookup"><span data-stu-id="63ce4-104">Syntax</span></span>  
  
```  
HRESULT GetTypeForTypeID(  
    [in] COR_TYPEID id, [  
    out] ICorDebugType **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="63ce4-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="63ce4-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="63ce4-106">[in]型識別子。</span><span class="sxs-lookup"><span data-stu-id="63ce4-106">[in] The type identifier.</span></span>  
  
 `ppType`  
 <span data-ttu-id="63ce4-107">[out]ICorDebugType オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="63ce4-107">[out] A pointer to the address of an ICorDebugType object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="63ce4-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="63ce4-108">Remarks</span></span>  
 <span data-ttu-id="63ce4-109">場合によっては、型識別子を返すメソッドは null を返す可能性があります`COR_TYPEID`値。</span><span class="sxs-lookup"><span data-stu-id="63ce4-109">In some cases, methods that return a type identifier may return a null `COR_TYPEID` value.</span></span> <span data-ttu-id="63ce4-110">としてこの値が渡された場合、`id`引数、`GetTypeForTypeID`メソッドは失敗し、返す`E_FAIL`します。</span><span class="sxs-lookup"><span data-stu-id="63ce4-110">If this value is passed as the `id` argument, the `GetTypeForTypeID` method will fail and return `E_FAIL`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63ce4-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="63ce4-111">Requirements</span></span>  
 <span data-ttu-id="63ce4-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="63ce4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63ce4-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="63ce4-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="63ce4-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63ce4-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63ce4-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63ce4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63ce4-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="63ce4-116">See also</span></span>

- [<span data-ttu-id="63ce4-117">ICorDebugProcess5 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="63ce4-117">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="63ce4-118">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="63ce4-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
