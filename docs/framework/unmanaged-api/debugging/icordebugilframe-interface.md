---
title: ICorDebugILFrame インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame
helpviewer_keywords:
- ICorDebugILFrame interface [.NET Framework debugging]
ms.assetid: d5cf5056-da4d-4629-914d-afe42a5393df
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0a40436fcf1485c5d08d175b0396af2b6870c19a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917018"
---
# <a name="icordebugilframe-interface"></a><span data-ttu-id="7955b-102">ICorDebugILFrame インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7955b-102">ICorDebugILFrame Interface</span></span>

<span data-ttu-id="7955b-103">Microsoft 中間言語 (MSIL) コードのスタックフレームを表します。</span><span class="sxs-lookup"><span data-stu-id="7955b-103">Represents a stack frame of Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="7955b-104">このインターフェイスは、テキストボックスのインターフェイスのサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="7955b-104">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7955b-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="7955b-105">Methods</span></span>  
  
|<span data-ttu-id="7955b-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="7955b-106">Method</span></span>|<span data-ttu-id="7955b-107">説明</span><span class="sxs-lookup"><span data-stu-id="7955b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7955b-108">CanSetIP メソッド</span><span class="sxs-lookup"><span data-stu-id="7955b-108">CanSetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-cansetip-method.md)|<span data-ttu-id="7955b-109">命令ポインターを指定したオフセット位置に安全に設定できるかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="7955b-109">Gets a value that indicates whether it is safe to set the instruction pointer to the specified offset location.</span></span>|  
|[<span data-ttu-id="7955b-110">EnumerateArguments メソッド</span><span class="sxs-lookup"><span data-stu-id="7955b-110">EnumerateArguments Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratearguments-method.md)|<span data-ttu-id="7955b-111">このフレーム内の引数の列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="7955b-111">Gets an enumerator for the arguments in this frame.</span></span>|  
|[<span data-ttu-id="7955b-112">EnumerateLocalVariables メソッド</span><span class="sxs-lookup"><span data-stu-id="7955b-112">EnumerateLocalVariables Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md)|<span data-ttu-id="7955b-113">このフレーム内のローカル変数の列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="7955b-113">Gets an enumerator for the local variables in this frame.</span></span>|  
|[<span data-ttu-id="7955b-114">GetArgument メソッド</span><span class="sxs-lookup"><span data-stu-id="7955b-114">GetArgument Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getargument-method.md)|<span data-ttu-id="7955b-115">この MSIL スタックフレーム内の指定された引数の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="7955b-115">Gets the value of the specified argument in this MSIL stack frame.</span></span>|  
|[<span data-ttu-id="7955b-116">GetIP メソッド</span><span class="sxs-lookup"><span data-stu-id="7955b-116">GetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md)|<span data-ttu-id="7955b-117">命令ポインターの値と、命令ポインターの値が取得された方法を示すビットごとの組み合わせ値を取得します。</span><span class="sxs-lookup"><span data-stu-id="7955b-117">Gets the value of the instruction pointer and a bitwise combination value that describes how the value of the instruction pointer was obtained.</span></span>|  
|[<span data-ttu-id="7955b-118">GetLocalVariable メソッド</span><span class="sxs-lookup"><span data-stu-id="7955b-118">GetLocalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md)|<span data-ttu-id="7955b-119">この MSIL スタックフレーム内の指定したローカル変数の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="7955b-119">Gets the value of the specified local variable in this MSIL stack frame.</span></span>|  
|[<span data-ttu-id="7955b-120">GetStackDepth メソッド</span><span class="sxs-lookup"><span data-stu-id="7955b-120">GetStackDepth Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getstackdepth-method.md)|<span data-ttu-id="7955b-121">実装されていません。</span><span class="sxs-lookup"><span data-stu-id="7955b-121">Not implemented.</span></span>|  
|[<span data-ttu-id="7955b-122">GetStackValue メソッド</span><span class="sxs-lookup"><span data-stu-id="7955b-122">GetStackValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getstackvalue-method.md)|<span data-ttu-id="7955b-123">実装されていません。</span><span class="sxs-lookup"><span data-stu-id="7955b-123">Not implemented.</span></span>|  
|[<span data-ttu-id="7955b-124">SetIP メソッド</span><span class="sxs-lookup"><span data-stu-id="7955b-124">SetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md)|<span data-ttu-id="7955b-125">命令ポインターを MSIL コード内の指定したオフセット位置に設定します。</span><span class="sxs-lookup"><span data-stu-id="7955b-125">Sets the instruction pointer to the specified offset location in the MSIL code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7955b-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="7955b-126">Remarks</span></span>  
 <span data-ttu-id="7955b-127">`ICorDebugILFrame`インターフェイスは、特別なテキストフレームインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="7955b-127">The `ICorDebugILFrame` interface is a specialized ICorDebugFrame interface.</span></span> <span data-ttu-id="7955b-128">これは、MSIL コードフレームまたは just-in-time (JIT) コンパイルフレームに対して使用されます。</span><span class="sxs-lookup"><span data-stu-id="7955b-128">It is used either for MSIL code frames or for just-in-time (JIT) compiled frames.</span></span> <span data-ttu-id="7955b-129">JIT でコンパイルされたフレームは`ICorDebugILFrame` 、インターフェイスとの両方のフレームインターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="7955b-129">The JIT-compiled frames implement both the `ICorDebugILFrame` interface and the ICorDebugNativeFrame interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7955b-130">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="7955b-130">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7955b-131">必要条件</span><span class="sxs-lookup"><span data-stu-id="7955b-131">Requirements</span></span>  
 <span data-ttu-id="7955b-132">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7955b-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7955b-133">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="7955b-133">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7955b-134">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="7955b-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7955b-135">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7955b-135">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7955b-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="7955b-136">See also</span></span>

- [<span data-ttu-id="7955b-137">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7955b-137">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
