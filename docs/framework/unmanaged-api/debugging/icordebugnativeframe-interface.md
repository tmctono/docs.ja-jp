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
ms.openlocfilehash: 41ac0b29ade2f78b893df72e8a17624373f6dd78
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792787"
---
# <a name="icordebugnativeframe-interface"></a><span data-ttu-id="5f99e-102">ICorDebugNativeFrame インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5f99e-102">ICorDebugNativeFrame Interface</span></span>

<span data-ttu-id="5f99e-103">ネイティブフレームに使用される、特殊な実装のテキストフレーム。</span><span class="sxs-lookup"><span data-stu-id="5f99e-103">A specialized implementation of ICorDebugFrame used for native frames.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5f99e-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="5f99e-104">Methods</span></span>  
  
|<span data-ttu-id="5f99e-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="5f99e-105">Method</span></span>|<span data-ttu-id="5f99e-106">説明</span><span class="sxs-lookup"><span data-stu-id="5f99e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5f99e-107">CanSetIP メソッド</span><span class="sxs-lookup"><span data-stu-id="5f99e-107">CanSetIP Method</span></span>](icordebugnativeframe-cansetip-method.md)|<span data-ttu-id="5f99e-108">命令ポインターをネイティブコード内の指定したオフセット位置に安全に設定できるかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="5f99e-108">Gets a value that indicates whether it is safe to set the instruction pointer to the specified offset location in native code.</span></span>|  
|[<span data-ttu-id="5f99e-109">GetIP メソッド</span><span class="sxs-lookup"><span data-stu-id="5f99e-109">GetIP Method</span></span>](icordebugnativeframe-getip-method.md)|<span data-ttu-id="5f99e-110">ネイティブコードへのスタックフレームのオフセットを取得します。</span><span class="sxs-lookup"><span data-stu-id="5f99e-110">Gets the stack frame's offset into native code.</span></span>|  
|[<span data-ttu-id="5f99e-111">GetLocalDoubleRegisterValue メソッド</span><span class="sxs-lookup"><span data-stu-id="5f99e-111">GetLocalDoubleRegisterValue Method</span></span>](icordebugnativeframe-getlocaldoubleregistervalue-method.md)|<span data-ttu-id="5f99e-112">ネイティブフレームの2つのメモリレジスタに格納されている引数またはローカル変数の値を表す ICorDebugValue へのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="5f99e-112">Gets a pointer to an ICorDebugValue that represents the value of an argument or local variable stored in two memory registers of a native frame.</span></span>|  
|[<span data-ttu-id="5f99e-113">GetLocalMemoryRegisterValue メソッド</span><span class="sxs-lookup"><span data-stu-id="5f99e-113">GetLocalMemoryRegisterValue Method</span></span>](icordebugnativeframe-getlocalmemoryregistervalue-method.md)|<span data-ttu-id="5f99e-114">指定したレジスタに下位ビットが格納されているローカル変数の値を表す `ICorDebugValue` へのポインターを取得します。上位ビットは、指定したメモリアドレスに格納されます。</span><span class="sxs-lookup"><span data-stu-id="5f99e-114">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable, of which the low bits are stored in the specified register and the high bits are stored at the specified memory address.</span></span>|  
|[<span data-ttu-id="5f99e-115">GetLocalMemoryValue メソッド</span><span class="sxs-lookup"><span data-stu-id="5f99e-115">GetLocalMemoryValue Method</span></span>](icordebugnativeframe-getlocalmemoryvalue-method.md)|<span data-ttu-id="5f99e-116">指定したメモリアドレスに格納されているローカル変数の値を表す `ICorDebugValue` へのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="5f99e-116">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable stored at the specified memory address.</span></span>|  
|[<span data-ttu-id="5f99e-117">GetLocalRegisterMemoryValue メソッド</span><span class="sxs-lookup"><span data-stu-id="5f99e-117">GetLocalRegisterMemoryValue Method</span></span>](icordebugnativeframe-getlocalregistermemoryvalue-method.md)|<span data-ttu-id="5f99e-118">指定したレジスタに上位ビットが格納され、指定したメモリアドレスに下位ビットが格納されているローカル変数の値を表す `ICorDebugValue` へのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="5f99e-118">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable, of which the high bits are stored in the specified register and the low bits are stored at the specified memory address</span></span>|  
|[<span data-ttu-id="5f99e-119">GetLocalRegisterValue メソッド</span><span class="sxs-lookup"><span data-stu-id="5f99e-119">GetLocalRegisterValue Method</span></span>](icordebugnativeframe-getlocalregistervalue-method.md)|<span data-ttu-id="5f99e-120">引数の値または指定したネイティブレジスタに格納されているローカル変数を表す `ICorDebugValue` へのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="5f99e-120">Gets a pointer to an `ICorDebugValue` that represents the value of an argument or a local variable stored in the specified native register.</span></span>|  
|[<span data-ttu-id="5f99e-121">GetRegisterSet メソッド</span><span class="sxs-lookup"><span data-stu-id="5f99e-121">GetRegisterSet Method</span></span>](icordebugnativeframe-getregisterset-method.md)|<span data-ttu-id="5f99e-122">この `ICorDebugNativeFrame`のレジスタセットを表す、[ツールセットへ](icordebugregisterset-interface.md)のポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="5f99e-122">Gets a pointer to an [ICorDebugRegisterSet](icordebugregisterset-interface.md) that represents the register set for this `ICorDebugNativeFrame`.</span></span>|  
|[<span data-ttu-id="5f99e-123">SetIP メソッド</span><span class="sxs-lookup"><span data-stu-id="5f99e-123">SetIP Method</span></span>](icordebugnativeframe-setip-method.md)|<span data-ttu-id="5f99e-124">命令ポインターをネイティブコード内の指定されたオフセット位置に設定します。</span><span class="sxs-lookup"><span data-stu-id="5f99e-124">Sets the instruction pointer to the specified offset location in native code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5f99e-125">コメント</span><span class="sxs-lookup"><span data-stu-id="5f99e-125">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5f99e-126">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="5f99e-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f99e-127">要件</span><span class="sxs-lookup"><span data-stu-id="5f99e-127">Requirements</span></span>  
 <span data-ttu-id="5f99e-128">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5f99e-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f99e-129">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5f99e-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5f99e-130">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5f99e-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5f99e-131">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f99e-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f99e-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="5f99e-132">See also</span></span>

- [<span data-ttu-id="5f99e-133">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5f99e-133">Debugging Interfaces</span></span>](debugging-interfaces.md)
