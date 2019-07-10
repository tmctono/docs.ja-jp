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
ms.openlocfilehash: f37fab4d877ae804996f46290e3576cecc5a25ca
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767618"
---
# <a name="icordebugprocess5gettypefortypeid-method"></a><span data-ttu-id="34518-102">ICorDebugProcess5::GetTypeForTypeID メソッド</span><span class="sxs-lookup"><span data-stu-id="34518-102">ICorDebugProcess5::GetTypeForTypeID Method</span></span>
<span data-ttu-id="34518-103">ICorDebugType 値を型識別子に変換します。</span><span class="sxs-lookup"><span data-stu-id="34518-103">Converts a type identifier to an ICorDebugType value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34518-104">構文</span><span class="sxs-lookup"><span data-stu-id="34518-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeForTypeID(  
    [in] COR_TYPEID id, [  
    out] ICorDebugType **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34518-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="34518-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="34518-106">[in]型識別子。</span><span class="sxs-lookup"><span data-stu-id="34518-106">[in] The type identifier.</span></span>  
  
 `ppType`  
 <span data-ttu-id="34518-107">[out]ICorDebugType オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="34518-107">[out] A pointer to the address of an ICorDebugType object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34518-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="34518-108">Remarks</span></span>  
 <span data-ttu-id="34518-109">場合によっては、型識別子を返すメソッドは null を返す可能性があります`COR_TYPEID`値。</span><span class="sxs-lookup"><span data-stu-id="34518-109">In some cases, methods that return a type identifier may return a null `COR_TYPEID` value.</span></span> <span data-ttu-id="34518-110">としてこの値が渡された場合、`id`引数、`GetTypeForTypeID`メソッドは失敗し、返す`E_FAIL`します。</span><span class="sxs-lookup"><span data-stu-id="34518-110">If this value is passed as the `id` argument, the `GetTypeForTypeID` method will fail and return `E_FAIL`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34518-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="34518-111">Requirements</span></span>  
 <span data-ttu-id="34518-112">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="34518-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34518-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="34518-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="34518-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="34518-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="34518-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34518-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34518-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="34518-116">See also</span></span>

- [<span data-ttu-id="34518-117">ICorDebugProcess5 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="34518-117">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="34518-118">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="34518-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
