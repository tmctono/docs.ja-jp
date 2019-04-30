---
title: ICorDebugExceptionDebugEvent::GetStackPointer メソッド
ms.date: 03/30/2017
ms.assetid: d8f66a1c-16be-4264-afc5-bc2dfbb4a682
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d9d4c0a1938edd3e2fe88ea6e418b3430f1b5cb8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995880"
---
# <a name="icordebugexceptiondebugeventgetstackpointer-method"></a><span data-ttu-id="9858d-102">ICorDebugExceptionDebugEvent::GetStackPointer メソッド</span><span class="sxs-lookup"><span data-stu-id="9858d-102">ICorDebugExceptionDebugEvent::GetStackPointer Method</span></span>
<span data-ttu-id="9858d-103">この例外デバッグ イベントのスタック ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="9858d-103">Gets the stack pointer for this exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9858d-104">構文</span><span class="sxs-lookup"><span data-stu-id="9858d-104">Syntax</span></span>  
  
```  
HRESULT GetStackPointer(  
   [out]CORDB_ADDRESS *pStackPointer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9858d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9858d-105">Parameters</span></span>  
 `pStackPointer`  
 <span data-ttu-id="9858d-106">[out] この例外デバッグ イベントのスタック ポインターのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="9858d-106">[out] A pointer to the address of the stack pointer for this exception debug event.</span></span> <span data-ttu-id="9858d-107">詳細については、次の「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9858d-107">See the Remarks section for more information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9858d-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="9858d-108">Remarks</span></span>  
 <span data-ttu-id="9858d-109">このスタック ポインターの意味は、次の表に示すように、イベントの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="9858d-109">The meaning of this stack pointer depends on the event type, as shown in the following table.</span></span>  
  
|<span data-ttu-id="9858d-110">イベントの種類</span><span class="sxs-lookup"><span data-stu-id="9858d-110">Event type</span></span>|<span data-ttu-id="9858d-111">`pStackPointer` 値の意味</span><span class="sxs-lookup"><span data-stu-id="9858d-111">Meaning of `pStackPointer` value</span></span>|  
|----------------|--------------------------------------|  
|[<span data-ttu-id="9858d-112">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="9858d-112">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="9858d-113">例外をスローしたフレームのスタック ポインター。</span><span class="sxs-lookup"><span data-stu-id="9858d-113">The stack pointer for the frame that threw the exception.</span></span>|  
|[<span data-ttu-id="9858d-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="9858d-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="9858d-115">スローされた例外の位置に最も近いユーザー コード フレームのスタック ポインター。</span><span class="sxs-lookup"><span data-stu-id="9858d-115">The stack pointer for the user-code frame closest to the point of the thrown exception.</span></span>|  
|[<span data-ttu-id="9858d-116">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="9858d-116">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="9858d-117">catch ハンドラーを含むフレームのスタック ポインター。</span><span class="sxs-lookup"><span data-stu-id="9858d-117">The stack pointer for the frame that contains the catch handler.</span></span>|  
|[<span data-ttu-id="9858d-118">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="9858d-118">MANAGED_EXCEPTION_UNHANDLED</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="9858d-119">`pStackPointer` が **null** です。</span><span class="sxs-lookup"><span data-stu-id="9858d-119">`pStackPointer` is **null**.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="9858d-120">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="9858d-120">This method is available with .NET Native only.</span></span>  
  
 <span data-ttu-id="9858d-121">イベントの種類がから利用可能な[icordebugdebugevent::geteventkind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="9858d-121">The event type is available from the [ICorDebugDebugEvent::GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9858d-122">必要条件</span><span class="sxs-lookup"><span data-stu-id="9858d-122">Requirements</span></span>  
 <span data-ttu-id="9858d-123">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9858d-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9858d-124">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9858d-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9858d-125">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9858d-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9858d-126">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9858d-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9858d-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="9858d-127">See also</span></span>

- [<span data-ttu-id="9858d-128">ICorDebugExceptionDebugEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9858d-128">ICorDebugExceptionDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="9858d-129">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9858d-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
