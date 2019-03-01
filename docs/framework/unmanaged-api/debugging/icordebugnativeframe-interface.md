---
title: ICorDebugNativeFrame インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame
helpviewer_keywords:
- ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 04819c58-7246-4b32-befb-680cf1dbc436
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fbdb17bcd502b75da0a73d9a36cf36d6564320bc
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "56975486"
---
# <a name="icordebugnativeframe-interface"></a><span data-ttu-id="3b83e-102">ICorDebugNativeFrame インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3b83e-102">ICorDebugNativeFrame Interface</span></span>

<span data-ttu-id="3b83e-103">ネイティブ フレームで使用される ICorDebugFrame の特殊な実装です。</span><span class="sxs-lookup"><span data-stu-id="3b83e-103">A specialized implementation of ICorDebugFrame used for native frames.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3b83e-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="3b83e-104">Methods</span></span>  
  
|<span data-ttu-id="3b83e-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="3b83e-105">Method</span></span>|<span data-ttu-id="3b83e-106">説明</span><span class="sxs-lookup"><span data-stu-id="3b83e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3b83e-107">CanSetIP メソッド</span><span class="sxs-lookup"><span data-stu-id="3b83e-107">CanSetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-cansetip-method.md)|<span data-ttu-id="3b83e-108">命令ポインターをネイティブ コードで指定されたオフセット位置に設定しても安全であるかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="3b83e-108">Gets a value that indicates whether it is safe to set the instruction pointer to the specified offset location in native code.</span></span>|  
|[<span data-ttu-id="3b83e-109">GetIP メソッド</span><span class="sxs-lookup"><span data-stu-id="3b83e-109">GetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getip-method.md)|<span data-ttu-id="3b83e-110">ネイティブ コードには、スタック フレームのオフセットを取得します。</span><span class="sxs-lookup"><span data-stu-id="3b83e-110">Gets the stack frame's offset into native code.</span></span>|  
|[<span data-ttu-id="3b83e-111">GetLocalDoubleRegisterValue メソッド</span><span class="sxs-lookup"><span data-stu-id="3b83e-111">GetLocalDoubleRegisterValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocaldoubleregistervalue-method.md)|<span data-ttu-id="3b83e-112">引数またはネイティブ フレームの 2 つのメモリ レジスタに格納されているローカル変数の値を表す ICorDebugValue へのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="3b83e-112">Gets a pointer to an ICorDebugValue that represents the value of an argument or local variable stored in two memory registers of a native frame.</span></span>|  
|[<span data-ttu-id="3b83e-113">GetLocalMemoryRegisterValue メソッド</span><span class="sxs-lookup"><span data-stu-id="3b83e-113">GetLocalMemoryRegisterValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalmemoryregistervalue-method.md)|<span data-ttu-id="3b83e-114">ポインターを取得、`ICorDebugValue`うち下位ビットが指定されたレジスタに格納されている、上位ビットが指定されたメモリ アドレスに格納されている、ローカル変数の値を表します。</span><span class="sxs-lookup"><span data-stu-id="3b83e-114">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable, of which the low bits are stored in the specified register and the high bits are stored at the specified memory address.</span></span>|  
|[<span data-ttu-id="3b83e-115">GetLocalMemoryValue メソッド</span><span class="sxs-lookup"><span data-stu-id="3b83e-115">GetLocalMemoryValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalmemoryvalue-method.md)|<span data-ttu-id="3b83e-116">ポインターを取得、`ICorDebugValue`を表す、指定されたメモリ アドレスに格納されているローカル変数の値。</span><span class="sxs-lookup"><span data-stu-id="3b83e-116">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable stored at the specified memory address.</span></span>|  
|[<span data-ttu-id="3b83e-117">GetLocalRegisterMemoryValue メソッド</span><span class="sxs-lookup"><span data-stu-id="3b83e-117">GetLocalRegisterMemoryValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalregistermemoryvalue-method.md)|<span data-ttu-id="3b83e-118">ポインターを取得、`ICorDebugValue`うち上位ビットが指定されたレジスタに格納されているし、指定されたメモリ アドレスの下位ビットが格納されている、ローカル変数の値を表す</span><span class="sxs-lookup"><span data-stu-id="3b83e-118">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable, of which the high bits are stored in the specified register and the low bits are stored at the specified memory address</span></span>|  
|[<span data-ttu-id="3b83e-119">GetLocalRegisterValue メソッド</span><span class="sxs-lookup"><span data-stu-id="3b83e-119">GetLocalRegisterValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalregistervalue-method.md)|<span data-ttu-id="3b83e-120">ポインターを取得、`ICorDebugValue`引数または指定されたネイティブ レジスタに格納されているローカル変数の値を表します。</span><span class="sxs-lookup"><span data-stu-id="3b83e-120">Gets a pointer to an `ICorDebugValue` that represents the value of an argument or a local variable stored in the specified native register.</span></span>|  
|[<span data-ttu-id="3b83e-121">GetRegisterSet メソッド</span><span class="sxs-lookup"><span data-stu-id="3b83e-121">GetRegisterSet Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getregisterset-method.md)|<span data-ttu-id="3b83e-122">ポインターを取得、 [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)これのレジスタ セットを表す`ICorDebugNativeFrame`します。</span><span class="sxs-lookup"><span data-stu-id="3b83e-122">Gets a pointer to an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) that represents the register set for this `ICorDebugNativeFrame`.</span></span>|  
|[<span data-ttu-id="3b83e-123">SetIP メソッド</span><span class="sxs-lookup"><span data-stu-id="3b83e-123">SetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md)|<span data-ttu-id="3b83e-124">命令ポインターをネイティブ コードで指定されたオフセット位置に設定します。</span><span class="sxs-lookup"><span data-stu-id="3b83e-124">Sets the instruction pointer to the specified offset location in native code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3b83e-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="3b83e-125">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3b83e-126">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="3b83e-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b83e-127">必要条件</span><span class="sxs-lookup"><span data-stu-id="3b83e-127">Requirements</span></span>  
 <span data-ttu-id="3b83e-128">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b83e-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b83e-129">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3b83e-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3b83e-130">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3b83e-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3b83e-131">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b83e-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b83e-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="3b83e-132">See also</span></span>
- [<span data-ttu-id="3b83e-133">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3b83e-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
