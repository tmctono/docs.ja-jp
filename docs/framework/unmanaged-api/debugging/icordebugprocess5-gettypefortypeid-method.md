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
ms.openlocfilehash: ea7f7a9d4589e4f08b1b1e20b4d073bb5f822714
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212764"
---
# <a name="icordebugprocess5gettypefortypeid-method"></a><span data-ttu-id="0202e-102">ICorDebugProcess5::GetTypeForTypeID メソッド</span><span class="sxs-lookup"><span data-stu-id="0202e-102">ICorDebugProcess5::GetTypeForTypeID Method</span></span>
<span data-ttu-id="0202e-103">型識別子をの型の値に変換します。</span><span class="sxs-lookup"><span data-stu-id="0202e-103">Converts a type identifier to an ICorDebugType value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0202e-104">構文</span><span class="sxs-lookup"><span data-stu-id="0202e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeForTypeID(  
    [in] COR_TYPEID id, [  
    out] ICorDebugType **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0202e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0202e-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="0202e-106">から型識別子。</span><span class="sxs-lookup"><span data-stu-id="0202e-106">[in] The type identifier.</span></span>  
  
 `ppType`  
 <span data-ttu-id="0202e-107">入出力テキストオブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="0202e-107">[out] A pointer to the address of an ICorDebugType object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0202e-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="0202e-108">Remarks</span></span>  
 <span data-ttu-id="0202e-109">場合によっては、型識別子を返すメソッドが null 値を返すことがあり `COR_TYPEID` ます。</span><span class="sxs-lookup"><span data-stu-id="0202e-109">In some cases, methods that return a type identifier may return a null `COR_TYPEID` value.</span></span> <span data-ttu-id="0202e-110">この値が引数として渡された場合 `id` 、 `GetTypeForTypeID` メソッドは失敗し、を返し `E_FAIL` ます。</span><span class="sxs-lookup"><span data-stu-id="0202e-110">If this value is passed as the `id` argument, the `GetTypeForTypeID` method will fail and return `E_FAIL`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0202e-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="0202e-111">Requirements</span></span>  
 <span data-ttu-id="0202e-112">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0202e-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0202e-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0202e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0202e-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0202e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0202e-115">**.NET Framework のバージョン:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0202e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0202e-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="0202e-116">See also</span></span>

- [<span data-ttu-id="0202e-117">ICorDebugProcess5 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0202e-117">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="0202e-118">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="0202e-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
