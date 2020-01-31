---
title: ICorDebugExceptionDebugEvent::GetNativeIP メソッド
ms.date: 03/30/2017
ms.assetid: 12e6a262-d9ac-49b8-9b80-1e653a2a3819
ms.openlocfilehash: 31af92dae47027b7285b422a05014b081d7e39a2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788686"
---
# <a name="icordebugexceptiondebugeventgetnativeip-method"></a><span data-ttu-id="875ac-102">ICorDebugExceptionDebugEvent::GetNativeIP メソッド</span><span class="sxs-lookup"><span data-stu-id="875ac-102">ICorDebugExceptionDebugEvent::GetNativeIP Method</span></span>
<span data-ttu-id="875ac-103">この例外デバッグ イベントのネイティブ命令ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="875ac-103">Gets the native instruction pointer for this exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="875ac-104">構文</span><span class="sxs-lookup"><span data-stu-id="875ac-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNativeIP(  
   [out]CORDB_ADDRESS *pIP  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="875ac-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="875ac-105">Parameters</span></span>  
 `pIP`  
 <span data-ttu-id="875ac-106">[out] この例外デバッグ イベントのネイティブ命令ポインターに対するポインター。</span><span class="sxs-lookup"><span data-stu-id="875ac-106">[out] A pointer to the instruction pointer for this exception debug event.</span></span> <span data-ttu-id="875ac-107">詳細については、次の「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="875ac-107">See the Remarks section for more information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="875ac-108">コメント</span><span class="sxs-lookup"><span data-stu-id="875ac-108">Remarks</span></span>  
 <span data-ttu-id="875ac-109">この命令ポインターの意味は、次の表に示すように、イベントの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="875ac-109">The meaning of this instruction pointer depends on the event type, as shown in the following table.</span></span>  
  
|<span data-ttu-id="875ac-110">イベントの種類</span><span class="sxs-lookup"><span data-stu-id="875ac-110">Event type</span></span>|<span data-ttu-id="875ac-111">`pStackPointer` 値の意味</span><span class="sxs-lookup"><span data-stu-id="875ac-111">Meaning of `pStackPointer` value</span></span>|  
|----------------|--------------------------------------|  
|[<span data-ttu-id="875ac-112">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="875ac-112">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="875ac-113">障害の発生した命令のアドレス。</span><span class="sxs-lookup"><span data-stu-id="875ac-113">The address of the faulting instruction.</span></span>|  
|[<span data-ttu-id="875ac-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="875ac-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="875ac-115">例外が発生しなかった場合に実行が再開される、 [Getstackpointer](icordebugexceptiondebugevent-getstackpointer-method.md)メソッドによって示されるフレーム内のコードアドレス。</span><span class="sxs-lookup"><span data-stu-id="875ac-115">The code address in the frame indicated by the [GetStackPointer](icordebugexceptiondebugevent-getstackpointer-method.md) method where execution would resume if no exception had been raised.</span></span> <span data-ttu-id="875ac-116">例外によって、`try/catch/finally` 句の catch ブロックなどの別のコードがこのフレーム内で実行される原因となることもあれば、そうでない場合もあります。</span><span class="sxs-lookup"><span data-stu-id="875ac-116">The exception may or may not cause different code, such as the catch block of a `try/catch/finally` clause, to be executed in this frame.</span></span>|  
|[<span data-ttu-id="875ac-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="875ac-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="875ac-118">[Getstackpointer](icordebugexceptiondebugevent-getstackpointer-method.md)メソッドによって示されるフレーム内で `catch` ハンドラーの実行が開始されるコードアドレス。</span><span class="sxs-lookup"><span data-stu-id="875ac-118">The code address where `catch` handler execution will start in the frame indicated by the [GetStackPointer](icordebugexceptiondebugevent-getstackpointer-method.md) method.</span></span>|  
|[<span data-ttu-id="875ac-119">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="875ac-119">MANAGED_EXCEPTION_UNHANDLED</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="875ac-120">`pIP` は 0 です。</span><span class="sxs-lookup"><span data-stu-id="875ac-120">`pIP` is 0.</span></span>|  
  
 <span data-ttu-id="875ac-121">イベントの種類は、テキスト形式の[イベント:: GetEventKind](icordebugdebugevent-geteventkind-method.md)メソッドから取得できます。</span><span class="sxs-lookup"><span data-stu-id="875ac-121">The event type is available from the [ICorDebugDebugEvent::GetEventKind](icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="875ac-122">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="875ac-122">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="875ac-123">要件</span><span class="sxs-lookup"><span data-stu-id="875ac-123">Requirements</span></span>  
 <span data-ttu-id="875ac-124">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="875ac-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="875ac-125">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="875ac-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="875ac-126">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="875ac-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="875ac-127">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="875ac-127">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="875ac-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="875ac-128">See also</span></span>

- [<span data-ttu-id="875ac-129">ICorDebugExceptionDebugEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="875ac-129">ICorDebugExceptionDebugEvent Interface</span></span>](icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="875ac-130">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="875ac-130">Debugging Interfaces</span></span>](debugging-interfaces.md)
