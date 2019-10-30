---
title: ICorDebugRegisterSet インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet
helpviewer_keywords:
- ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: d3d9676d-0b87-4bc3-b679-7bbc7a186c88
topic_type:
- apiref
ms.openlocfilehash: 1ea0274adc12f3a99df0422bfc0b5180f0ef5596
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131379"
---
# <a name="icordebugregisterset-interface"></a><span data-ttu-id="2fa3f-102">ICorDebugRegisterSet インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2fa3f-102">ICorDebugRegisterSet Interface</span></span>
<span data-ttu-id="2fa3f-103">現在コードを実行しているコンピューターで使用できるレジスタのセットを表します。</span><span class="sxs-lookup"><span data-stu-id="2fa3f-103">Represents the set of registers available on the computer that is currently executing code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2fa3f-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="2fa3f-104">Methods</span></span>  
  
|<span data-ttu-id="2fa3f-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="2fa3f-105">Method</span></span>|<span data-ttu-id="2fa3f-106">説明</span><span class="sxs-lookup"><span data-stu-id="2fa3f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2fa3f-107">GetRegisters メソッド</span><span class="sxs-lookup"><span data-stu-id="2fa3f-107">GetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregisters-method.md)|<span data-ttu-id="2fa3f-108">ビットマスクによって指定された、(現在コードを実行しているコンピューター上の) 各レジスタの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="2fa3f-108">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>|  
|[<span data-ttu-id="2fa3f-109">GetRegistersAvailable メソッド</span><span class="sxs-lookup"><span data-stu-id="2fa3f-109">GetRegistersAvailable Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md)|<span data-ttu-id="2fa3f-110">この `ICorDebugRegisterSet` 内のどのレジスタが現在使用可能であるかを示すビットマスクを取得します。</span><span class="sxs-lookup"><span data-stu-id="2fa3f-110">Gets a bit mask indicating which registers in this `ICorDebugRegisterSet` are currently available.</span></span>|  
|[<span data-ttu-id="2fa3f-111">GetThreadContext メソッド</span><span class="sxs-lookup"><span data-stu-id="2fa3f-111">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getthreadcontext-method.md)|<span data-ttu-id="2fa3f-112">現在のスレッドのコンテキストを取得します。</span><span class="sxs-lookup"><span data-stu-id="2fa3f-112">Gets the context of the current thread.</span></span>|  
|[<span data-ttu-id="2fa3f-113">SetRegisters メソッド</span><span class="sxs-lookup"><span data-stu-id="2fa3f-113">SetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-setregisters-method.md)|<span data-ttu-id="2fa3f-114">.NET Framework バージョン2.0 には実装されていません。</span><span class="sxs-lookup"><span data-stu-id="2fa3f-114">Not implemented for the .NET Framework version 2.0.</span></span>|  
|[<span data-ttu-id="2fa3f-115">SetThreadContext メソッド</span><span class="sxs-lookup"><span data-stu-id="2fa3f-115">SetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-setthreadcontext-method.md)|<span data-ttu-id="2fa3f-116">.NET Framework 2.0 には実装されていません。</span><span class="sxs-lookup"><span data-stu-id="2fa3f-116">Not implemented for the .NET Framework 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2fa3f-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="2fa3f-117">Remarks</span></span>  
 <span data-ttu-id="2fa3f-118">`ICorDebugRegisterSet` インターフェイスでは、32ビットのレジスタのみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="2fa3f-118">The `ICorDebugRegisterSet` interface supports only 32-bit registers.</span></span> <span data-ttu-id="2fa3f-119">追加のレジスタを必要とする IA-64 などのプラットフォームで[ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)インターフェイスを使用します。</span><span class="sxs-lookup"><span data-stu-id="2fa3f-119">Use the [ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md) interface on platforms such as IA-64 that require additional registers.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2fa3f-120">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="2fa3f-120">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2fa3f-121">［要件］</span><span class="sxs-lookup"><span data-stu-id="2fa3f-121">Requirements</span></span>  
 <span data-ttu-id="2fa3f-122">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2fa3f-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2fa3f-123">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2fa3f-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2fa3f-124">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2fa3f-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2fa3f-125">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2fa3f-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fa3f-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="2fa3f-126">See also</span></span>

- [<span data-ttu-id="2fa3f-127">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2fa3f-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="2fa3f-128">ICorDebugRegisterSet2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2fa3f-128">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
