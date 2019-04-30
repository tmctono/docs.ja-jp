---
title: ICorDebugILFrame3::GetReturnValueForILOffset メソッド
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
api_name:
- ICorDebugILFrame3.GetReturnValueForILOffset
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 06522727-5f64-4391-9331-11386883c352
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7ac90473a0bf15173683c45abc8e4a840ea7e733
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946434"
---
# <a name="icordebugilframe3getreturnvalueforiloffset-method"></a><span data-ttu-id="2e91d-102">ICorDebugILFrame3::GetReturnValueForILOffset メソッド</span><span class="sxs-lookup"><span data-stu-id="2e91d-102">ICorDebugILFrame3::GetReturnValueForILOffset Method</span></span>
<span data-ttu-id="2e91d-103">関数の戻り値をカプセル化する"ICorDebugValue"オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="2e91d-103">Gets an "ICorDebugValue" object that encapsulates the return value of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e91d-104">構文</span><span class="sxs-lookup"><span data-stu-id="2e91d-104">Syntax</span></span>  
  
```cpp
HRESULT GetReturnValueForILOffset(  
    ULONG32 ILoffset,   
    [out] ICorDebugValue **ppReturnValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2e91d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2e91d-105">Parameters</span></span>  
 `ILOffset`  
 <span data-ttu-id="2e91d-106">オフセット IL。</span><span class="sxs-lookup"><span data-stu-id="2e91d-106">The IL offset.</span></span> <span data-ttu-id="2e91d-107">「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e91d-107">See the Remarks section.</span></span>  
  
 `ppReturnValue`  
 <span data-ttu-id="2e91d-108">関数呼び出しの戻り値に関する情報を提供する"ICorDebugValue"インターフェイス オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="2e91d-108">A pointer to the address of an "ICorDebugValue" interface object that provides information about the return value of a function call.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2e91d-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="2e91d-109">Remarks</span></span>  
 <span data-ttu-id="2e91d-110">このメソッドはと共に使用、 [icordebugcode 3::getreturnvalueliveoffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md)メソッドの戻り値を取得します。</span><span class="sxs-lookup"><span data-stu-id="2e91d-110">This method is used along with the [ICorDebugCode3::GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) method to get the return value of a method.</span></span> <span data-ttu-id="2e91d-111">次の 2 つのコード例で示すように、これは戻り値が無視されるメソッドの場合に特に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2e91d-111">It is particularly useful in the case of methods whose return values are ignored, as in the following two code examples.</span></span> <span data-ttu-id="2e91d-112">1 番目の例では、<xref:System.Int32.TryParse%2A?displayProperty=nameWithType> メソッドを呼び出しますが、メソッドの戻り値を無視します。</span><span class="sxs-lookup"><span data-stu-id="2e91d-112">The first example calls the <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> method, but ignores the method's return value.</span></span>  
  
 [!code-csharp[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv1.cs#1)]
 [!code-vb[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv1.vb#1)]  
  
 <span data-ttu-id="2e91d-113">2 番目の例は、より一般的なデバッグの問題を示しています。</span><span class="sxs-lookup"><span data-stu-id="2e91d-113">The second example illustrates a much more common problem in debugging.</span></span> <span data-ttu-id="2e91d-114">メソッド呼び出しで引数としてメソッドが使用されるため、デバッガーで呼び出されたメソッドをステップ実行する場合に限り、戻り値にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2e91d-114">Because a method is used as an argument in a method call, its return value is accessible only when the debugger steps through the called method.</span></span> <span data-ttu-id="2e91d-115">多くの場合、特に呼び出されたメソッドが外部ライブラリで定義されている場合にはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="2e91d-115">In many cases, particularly when the called method is defined in an external library, that is not possible.</span></span>  
  
 [!code-csharp[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv2.cs#2)]
 [!code-vb[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv2.vb#2)]  
  
 <span data-ttu-id="2e91d-116">渡す場合、 [icordebugcode 3::getreturnvalueliveoffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md)メソッド、関数呼び出しサイトへの IL オフセットを 1 つまたは複数のネイティブ オフセット返します。</span><span class="sxs-lookup"><span data-stu-id="2e91d-116">If you pass the [ICorDebugCode3::GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) method an IL offset to a function call site, it returns one or more native offsets.</span></span> <span data-ttu-id="2e91d-117">これによってデバッガーは、関数内のこうしたネイティブ オフセット上でブレークポイントを設定できます。</span><span class="sxs-lookup"><span data-stu-id="2e91d-117">The debugger can then set breakpoints on these native offsets in the function.</span></span> <span data-ttu-id="2e91d-118">デバッガーがいずれかのブレークポイントに到達すると、戻り値を取得するためにこのメソッドに同じ IL オフセットを渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="2e91d-118">When the debugger hits one of the breakpoints, you can then pass the same IL offset that you passed to this method to get the return value.</span></span> <span data-ttu-id="2e91d-119">この場合、デバッガーは設定したブレークポイントすべてをクリアする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e91d-119">The debugger should then clear all the breakpoints that it set.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="2e91d-120">[Icordebugcode 3::getreturnvalueliveoffset メソッド](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md)と`ICorDebugILFrame3::GetReturnValueForILOffset`メソッドでは、参照型だけの戻り値の情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="2e91d-120">The [ICorDebugCode3::GetReturnValueLiveOffset Method](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) and `ICorDebugILFrame3::GetReturnValueForILOffset` methods allow you to get return value information for reference types only.</span></span> <span data-ttu-id="2e91d-121">値型 (つまり、<xref:System.ValueType> から派生するすべての型) からの戻り値情報の取得はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="2e91d-121">Retrieving return value information from value types (that is, all types that derive from <xref:System.ValueType>) is not supported.</span></span>  
  
 <span data-ttu-id="2e91d-122">指定された IL オフセット、`ILOffset`パラメーターは、関数呼び出しサイトでは、によって返されるネイティブ オフセットに設定されたブレークポイントでデバッガーを停止するか、 [icordebugcode 3::getreturnvalueliveoffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md)メソッド同じ IL オフセット。</span><span class="sxs-lookup"><span data-stu-id="2e91d-122">The IL offset specified by the `ILOffset` parameter should be at a function call site, and the debuggee should be stopped at a breakpoint set at the native offset returned by the [ICorDebugCode3::GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) method for the same IL offset.</span></span> <span data-ttu-id="2e91d-123">デバッグ対象が指定の IL オフセットに対して正確な場所で停止しない場合、API は失敗します。</span><span class="sxs-lookup"><span data-stu-id="2e91d-123">If the debuggee is not stopped at the correct location for the specified IL offset, the API will fail.</span></span>  
  
 <span data-ttu-id="2e91d-124">関数呼び出しで値が返されない場合、API は失敗します。</span><span class="sxs-lookup"><span data-stu-id="2e91d-124">If the function call doesn't return a value, the API will fail.</span></span>  
  
 <span data-ttu-id="2e91d-125">`ICorDebugILFrame3::GetReturnValueForILOffset` メソッドは、x86 ベースおよび AMD64 システムでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="2e91d-125">The `ICorDebugILFrame3::GetReturnValueForILOffset` method is available only on x86-based and AMD64 systems.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e91d-126">必要条件</span><span class="sxs-lookup"><span data-stu-id="2e91d-126">Requirements</span></span>  
 <span data-ttu-id="2e91d-127">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e91d-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e91d-128">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2e91d-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2e91d-129">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2e91d-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2e91d-130">**.NET Framework のバージョン:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e91d-130">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e91d-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="2e91d-131">See also</span></span>

- [<span data-ttu-id="2e91d-132">GetReturnValueLiveOffSet メソッド</span><span class="sxs-lookup"><span data-stu-id="2e91d-132">GetReturnValueLiveOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md)
- [<span data-ttu-id="2e91d-133">ICorDebugILFrame3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2e91d-133">ICorDebugILFrame3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-interface.md)
