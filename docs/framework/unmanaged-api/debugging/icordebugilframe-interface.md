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
ms.openlocfilehash: 1c60d7685de1e9a1d4f631ad1fba53b981829f58
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988586"
---
# <a name="icordebugilframe-interface"></a><span data-ttu-id="39aac-102">ICorDebugILFrame インターフェイス</span><span class="sxs-lookup"><span data-stu-id="39aac-102">ICorDebugILFrame Interface</span></span>

<span data-ttu-id="39aac-103">Microsoft intermediate language (MSIL) コードのスタック フレームを表します。</span><span class="sxs-lookup"><span data-stu-id="39aac-103">Represents a stack frame of Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="39aac-104">このインターフェイスは、ICorDebugFrame インターフェイスのサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="39aac-104">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="39aac-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="39aac-105">Methods</span></span>  
  
|<span data-ttu-id="39aac-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="39aac-106">Method</span></span>|<span data-ttu-id="39aac-107">説明</span><span class="sxs-lookup"><span data-stu-id="39aac-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="39aac-108">CanSetIP メソッド</span><span class="sxs-lookup"><span data-stu-id="39aac-108">CanSetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-cansetip-method.md)|<span data-ttu-id="39aac-109">命令ポインターを指定したオフセット位置に設定しても安全であるかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="39aac-109">Gets a value that indicates whether it is safe to set the instruction pointer to the specified offset location.</span></span>|  
|[<span data-ttu-id="39aac-110">EnumerateArguments メソッド</span><span class="sxs-lookup"><span data-stu-id="39aac-110">EnumerateArguments Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratearguments-method.md)|<span data-ttu-id="39aac-111">このフレームで、引数の列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="39aac-111">Gets an enumerator for the arguments in this frame.</span></span>|  
|[<span data-ttu-id="39aac-112">EnumerateLocalVariables メソッド</span><span class="sxs-lookup"><span data-stu-id="39aac-112">EnumerateLocalVariables Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md)|<span data-ttu-id="39aac-113">このフレームでローカル変数の列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="39aac-113">Gets an enumerator for the local variables in this frame.</span></span>|  
|[<span data-ttu-id="39aac-114">GetArgument メソッド</span><span class="sxs-lookup"><span data-stu-id="39aac-114">GetArgument Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getargument-method.md)|<span data-ttu-id="39aac-115">この MSIL のスタック フレーム内には、指定された引数の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="39aac-115">Gets the value of the specified argument in this MSIL stack frame.</span></span>|  
|[<span data-ttu-id="39aac-116">GetIP メソッド</span><span class="sxs-lookup"><span data-stu-id="39aac-116">GetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md)|<span data-ttu-id="39aac-117">命令ポインターの値と命令ポインターの値の取得方法を示すビットごとの組み合わせ値を取得します。</span><span class="sxs-lookup"><span data-stu-id="39aac-117">Gets the value of the instruction pointer and a bitwise combination value that describes how the value of the instruction pointer was obtained.</span></span>|  
|[<span data-ttu-id="39aac-118">GetLocalVariable メソッド</span><span class="sxs-lookup"><span data-stu-id="39aac-118">GetLocalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md)|<span data-ttu-id="39aac-119">この MSIL のスタック フレーム内には、指定されたローカル変数の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="39aac-119">Gets the value of the specified local variable in this MSIL stack frame.</span></span>|  
|[<span data-ttu-id="39aac-120">GetStackDepth メソッド</span><span class="sxs-lookup"><span data-stu-id="39aac-120">GetStackDepth Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getstackdepth-method.md)|<span data-ttu-id="39aac-121">実装されていません。</span><span class="sxs-lookup"><span data-stu-id="39aac-121">Not implemented.</span></span>|  
|[<span data-ttu-id="39aac-122">GetStackValue メソッド</span><span class="sxs-lookup"><span data-stu-id="39aac-122">GetStackValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getstackvalue-method.md)|<span data-ttu-id="39aac-123">実装されていません。</span><span class="sxs-lookup"><span data-stu-id="39aac-123">Not implemented.</span></span>|  
|[<span data-ttu-id="39aac-124">SetIP メソッド</span><span class="sxs-lookup"><span data-stu-id="39aac-124">SetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md)|<span data-ttu-id="39aac-125">MSIL コード内の指定したオフセット位置に、命令ポインターを設定します。</span><span class="sxs-lookup"><span data-stu-id="39aac-125">Sets the instruction pointer to the specified offset location in the MSIL code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39aac-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="39aac-126">Remarks</span></span>  
 <span data-ttu-id="39aac-127">`ICorDebugILFrame`インターフェイスは特殊な ICorDebugFrame インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="39aac-127">The `ICorDebugILFrame` interface is a specialized ICorDebugFrame interface.</span></span> <span data-ttu-id="39aac-128">使用される MSIL コードのフレームまたは・ イン タイム (JIT) コンパイル済みのフレーム。</span><span class="sxs-lookup"><span data-stu-id="39aac-128">It is used either for MSIL code frames or for just-in-time (JIT) compiled frames.</span></span> <span data-ttu-id="39aac-129">JIT コンパイルされたフレームでは、両方を実装、`ICorDebugILFrame`インターフェイスと ICorDebugNativeFrame インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="39aac-129">The JIT-compiled frames implement both the `ICorDebugILFrame` interface and the ICorDebugNativeFrame interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="39aac-130">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="39aac-130">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39aac-131">必要条件</span><span class="sxs-lookup"><span data-stu-id="39aac-131">Requirements</span></span>  
 <span data-ttu-id="39aac-132">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="39aac-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39aac-133">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="39aac-133">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="39aac-134">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="39aac-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="39aac-135">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39aac-135">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39aac-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="39aac-136">See also</span></span>

- [<span data-ttu-id="39aac-137">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="39aac-137">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
