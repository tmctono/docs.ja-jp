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
ms.openlocfilehash: 04bdbc49217236bc6c05a718cb4d42067cafd8bf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73096675"
---
# <a name="icordebugnativeframe-interface"></a><span data-ttu-id="34407-102">ICorDebugNativeFrame インターフェイス</span><span class="sxs-lookup"><span data-stu-id="34407-102">ICorDebugNativeFrame Interface</span></span>

<span data-ttu-id="34407-103">ネイティブフレームに使用される、特殊な実装のテキストフレーム。</span><span class="sxs-lookup"><span data-stu-id="34407-103">A specialized implementation of ICorDebugFrame used for native frames.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="34407-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="34407-104">Methods</span></span>  
  
|<span data-ttu-id="34407-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="34407-105">Method</span></span>|<span data-ttu-id="34407-106">説明</span><span class="sxs-lookup"><span data-stu-id="34407-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="34407-107">CanSetIP メソッド</span><span class="sxs-lookup"><span data-stu-id="34407-107">CanSetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-cansetip-method.md)|<span data-ttu-id="34407-108">命令ポインターをネイティブコード内の指定したオフセット位置に安全に設定できるかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="34407-108">Gets a value that indicates whether it is safe to set the instruction pointer to the specified offset location in native code.</span></span>|  
|[<span data-ttu-id="34407-109">GetIP メソッド</span><span class="sxs-lookup"><span data-stu-id="34407-109">GetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getip-method.md)|<span data-ttu-id="34407-110">ネイティブコードへのスタックフレームのオフセットを取得します。</span><span class="sxs-lookup"><span data-stu-id="34407-110">Gets the stack frame's offset into native code.</span></span>|  
|[<span data-ttu-id="34407-111">GetLocalDoubleRegisterValue メソッド</span><span class="sxs-lookup"><span data-stu-id="34407-111">GetLocalDoubleRegisterValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocaldoubleregistervalue-method.md)|<span data-ttu-id="34407-112">ネイティブフレームの2つのメモリレジスタに格納されている引数またはローカル変数の値を表す ICorDebugValue へのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="34407-112">Gets a pointer to an ICorDebugValue that represents the value of an argument or local variable stored in two memory registers of a native frame.</span></span>|  
|[<span data-ttu-id="34407-113">GetLocalMemoryRegisterValue メソッド</span><span class="sxs-lookup"><span data-stu-id="34407-113">GetLocalMemoryRegisterValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalmemoryregistervalue-method.md)|<span data-ttu-id="34407-114">指定したレジスタに下位ビットが格納されているローカル変数の値を表す `ICorDebugValue` へのポインターを取得します。上位ビットは、指定したメモリアドレスに格納されます。</span><span class="sxs-lookup"><span data-stu-id="34407-114">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable, of which the low bits are stored in the specified register and the high bits are stored at the specified memory address.</span></span>|  
|[<span data-ttu-id="34407-115">GetLocalMemoryValue メソッド</span><span class="sxs-lookup"><span data-stu-id="34407-115">GetLocalMemoryValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalmemoryvalue-method.md)|<span data-ttu-id="34407-116">指定したメモリアドレスに格納されているローカル変数の値を表す `ICorDebugValue` へのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="34407-116">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable stored at the specified memory address.</span></span>|  
|[<span data-ttu-id="34407-117">GetLocalRegisterMemoryValue メソッド</span><span class="sxs-lookup"><span data-stu-id="34407-117">GetLocalRegisterMemoryValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalregistermemoryvalue-method.md)|<span data-ttu-id="34407-118">指定したレジスタに上位ビットが格納され、指定したメモリアドレスに下位ビットが格納されているローカル変数の値を表す `ICorDebugValue` へのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="34407-118">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable, of which the high bits are stored in the specified register and the low bits are stored at the specified memory address</span></span>|  
|[<span data-ttu-id="34407-119">GetLocalRegisterValue メソッド</span><span class="sxs-lookup"><span data-stu-id="34407-119">GetLocalRegisterValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalregistervalue-method.md)|<span data-ttu-id="34407-120">引数の値または指定したネイティブレジスタに格納されているローカル変数を表す `ICorDebugValue` へのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="34407-120">Gets a pointer to an `ICorDebugValue` that represents the value of an argument or a local variable stored in the specified native register.</span></span>|  
|[<span data-ttu-id="34407-121">GetRegisterSet メソッド</span><span class="sxs-lookup"><span data-stu-id="34407-121">GetRegisterSet Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getregisterset-method.md)|<span data-ttu-id="34407-122">この `ICorDebugNativeFrame`のレジスタセットを表す、[ツールセットへ](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)のポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="34407-122">Gets a pointer to an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) that represents the register set for this `ICorDebugNativeFrame`.</span></span>|  
|[<span data-ttu-id="34407-123">SetIP メソッド</span><span class="sxs-lookup"><span data-stu-id="34407-123">SetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md)|<span data-ttu-id="34407-124">命令ポインターをネイティブコード内の指定されたオフセット位置に設定します。</span><span class="sxs-lookup"><span data-stu-id="34407-124">Sets the instruction pointer to the specified offset location in native code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34407-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="34407-125">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="34407-126">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="34407-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34407-127">［要件］</span><span class="sxs-lookup"><span data-stu-id="34407-127">Requirements</span></span>  
 <span data-ttu-id="34407-128">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34407-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34407-129">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="34407-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="34407-130">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="34407-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="34407-131">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34407-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34407-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="34407-132">See also</span></span>

- [<span data-ttu-id="34407-133">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="34407-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
