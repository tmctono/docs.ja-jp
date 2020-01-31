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
ms.openlocfilehash: bb25c9235e4fcded5c230d2d417b9d41bbdd9b19
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792335"
---
# <a name="icordebugprocess5gettypefortypeid-method"></a><span data-ttu-id="d744f-102">ICorDebugProcess5::GetTypeForTypeID メソッド</span><span class="sxs-lookup"><span data-stu-id="d744f-102">ICorDebugProcess5::GetTypeForTypeID Method</span></span>
<span data-ttu-id="d744f-103">型識別子をの型の値に変換します。</span><span class="sxs-lookup"><span data-stu-id="d744f-103">Converts a type identifier to an ICorDebugType value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d744f-104">構文</span><span class="sxs-lookup"><span data-stu-id="d744f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeForTypeID(  
    [in] COR_TYPEID id, [  
    out] ICorDebugType **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d744f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d744f-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="d744f-106">から型識別子。</span><span class="sxs-lookup"><span data-stu-id="d744f-106">[in] The type identifier.</span></span>  
  
 `ppType`  
 <span data-ttu-id="d744f-107">入出力テキストオブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d744f-107">[out] A pointer to the address of an ICorDebugType object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d744f-108">コメント</span><span class="sxs-lookup"><span data-stu-id="d744f-108">Remarks</span></span>  
 <span data-ttu-id="d744f-109">場合によっては、型識別子を返すメソッドが null `COR_TYPEID` 値を返すことがあります。</span><span class="sxs-lookup"><span data-stu-id="d744f-109">In some cases, methods that return a type identifier may return a null `COR_TYPEID` value.</span></span> <span data-ttu-id="d744f-110">この値が `id` 引数として渡された場合、`GetTypeForTypeID` メソッドは失敗し、`E_FAIL`が返されます。</span><span class="sxs-lookup"><span data-stu-id="d744f-110">If this value is passed as the `id` argument, the `GetTypeForTypeID` method will fail and return `E_FAIL`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d744f-111">要件</span><span class="sxs-lookup"><span data-stu-id="d744f-111">Requirements</span></span>  
 <span data-ttu-id="d744f-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d744f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d744f-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d744f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d744f-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d744f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d744f-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d744f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d744f-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="d744f-116">See also</span></span>

- [<span data-ttu-id="d744f-117">ICorDebugProcess5 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d744f-117">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="d744f-118">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d744f-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
