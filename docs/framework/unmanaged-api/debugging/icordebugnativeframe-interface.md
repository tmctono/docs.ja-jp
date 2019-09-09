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
ms.openlocfilehash: c01346b42fff812f8358482ae0e8570c03ee9231
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912801"
---
# <a name="icordebugnativeframe-interface"></a><span data-ttu-id="5b48f-102">ICorDebugNativeFrame インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5b48f-102">ICorDebugNativeFrame Interface</span></span>

<span data-ttu-id="5b48f-103">ネイティブフレームに使用される、特殊な実装のテキストフレーム。</span><span class="sxs-lookup"><span data-stu-id="5b48f-103">A specialized implementation of ICorDebugFrame used for native frames.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5b48f-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="5b48f-104">Methods</span></span>  
  
|<span data-ttu-id="5b48f-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="5b48f-105">Method</span></span>|<span data-ttu-id="5b48f-106">説明</span><span class="sxs-lookup"><span data-stu-id="5b48f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5b48f-107">CanSetIP メソッド</span><span class="sxs-lookup"><span data-stu-id="5b48f-107">CanSetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-cansetip-method.md)|<span data-ttu-id="5b48f-108">命令ポインターをネイティブコード内の指定したオフセット位置に安全に設定できるかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="5b48f-108">Gets a value that indicates whether it is safe to set the instruction pointer to the specified offset location in native code.</span></span>|  
|[<span data-ttu-id="5b48f-109">GetIP メソッド</span><span class="sxs-lookup"><span data-stu-id="5b48f-109">GetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getip-method.md)|<span data-ttu-id="5b48f-110">ネイティブコードへのスタックフレームのオフセットを取得します。</span><span class="sxs-lookup"><span data-stu-id="5b48f-110">Gets the stack frame's offset into native code.</span></span>|  
|[<span data-ttu-id="5b48f-111">GetLocalDoubleRegisterValue メソッド</span><span class="sxs-lookup"><span data-stu-id="5b48f-111">GetLocalDoubleRegisterValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocaldoubleregistervalue-method.md)|<span data-ttu-id="5b48f-112">ネイティブフレームの2つのメモリレジスタに格納されている引数またはローカル変数の値を表す ICorDebugValue へのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="5b48f-112">Gets a pointer to an ICorDebugValue that represents the value of an argument or local variable stored in two memory registers of a native frame.</span></span>|  
|[<span data-ttu-id="5b48f-113">GetLocalMemoryRegisterValue メソッド</span><span class="sxs-lookup"><span data-stu-id="5b48f-113">GetLocalMemoryRegisterValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalmemoryregistervalue-method.md)|<span data-ttu-id="5b48f-114">指定したレジスタに`ICorDebugValue`下位ビットが格納されているローカル変数の値を表すへのポインターを取得します。上位ビットは、指定したメモリアドレスに格納されます。</span><span class="sxs-lookup"><span data-stu-id="5b48f-114">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable, of which the low bits are stored in the specified register and the high bits are stored at the specified memory address.</span></span>|  
|[<span data-ttu-id="5b48f-115">GetLocalMemoryValue メソッド</span><span class="sxs-lookup"><span data-stu-id="5b48f-115">GetLocalMemoryValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalmemoryvalue-method.md)|<span data-ttu-id="5b48f-116">指定したメモリアドレス`ICorDebugValue`に格納されているローカル変数の値を表すへのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="5b48f-116">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable stored at the specified memory address.</span></span>|  
|[<span data-ttu-id="5b48f-117">GetLocalRegisterMemoryValue メソッド</span><span class="sxs-lookup"><span data-stu-id="5b48f-117">GetLocalRegisterMemoryValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalregistermemoryvalue-method.md)|<span data-ttu-id="5b48f-118">指定したレジスタに`ICorDebugValue`上位ビットが格納され、下位ビットが指定したメモリアドレスに格納されているローカル変数の値を表すへのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="5b48f-118">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable, of which the high bits are stored in the specified register and the low bits are stored at the specified memory address</span></span>|  
|[<span data-ttu-id="5b48f-119">GetLocalRegisterValue メソッド</span><span class="sxs-lookup"><span data-stu-id="5b48f-119">GetLocalRegisterValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalregistervalue-method.md)|<span data-ttu-id="5b48f-120">引数の値または`ICorDebugValue`指定したネイティブレジスタに格納されているローカル変数を表すへのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="5b48f-120">Gets a pointer to an `ICorDebugValue` that represents the value of an argument or a local variable stored in the specified native register.</span></span>|  
|[<span data-ttu-id="5b48f-121">GetRegisterSet メソッド</span><span class="sxs-lookup"><span data-stu-id="5b48f-121">GetRegisterSet Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getregisterset-method.md)|<span data-ttu-id="5b48f-122">この`ICorDebugNativeFrame`のレジスタセットを表す、ツール[のセットへ](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)のポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="5b48f-122">Gets a pointer to an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) that represents the register set for this `ICorDebugNativeFrame`.</span></span>|  
|[<span data-ttu-id="5b48f-123">SetIP メソッド</span><span class="sxs-lookup"><span data-stu-id="5b48f-123">SetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md)|<span data-ttu-id="5b48f-124">命令ポインターをネイティブコード内の指定されたオフセット位置に設定します。</span><span class="sxs-lookup"><span data-stu-id="5b48f-124">Sets the instruction pointer to the specified offset location in native code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5b48f-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="5b48f-125">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5b48f-126">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="5b48f-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b48f-127">必要条件</span><span class="sxs-lookup"><span data-stu-id="5b48f-127">Requirements</span></span>  
 <span data-ttu-id="5b48f-128">**・**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b48f-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b48f-129">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="5b48f-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5b48f-130">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="5b48f-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5b48f-131">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b48f-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b48f-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="5b48f-132">See also</span></span>

- [<span data-ttu-id="5b48f-133">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5b48f-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
