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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6419a525a8a542295751defb97e67a83220730b2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965065"
---
# <a name="icordebugregisterset-interface"></a><span data-ttu-id="2a583-102">ICorDebugRegisterSet インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2a583-102">ICorDebugRegisterSet Interface</span></span>
<span data-ttu-id="2a583-103">現在コードを実行しているコンピューターで使用できるレジスタのセットを表します。</span><span class="sxs-lookup"><span data-stu-id="2a583-103">Represents the set of registers available on the computer that is currently executing code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2a583-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="2a583-104">Methods</span></span>  
  
|<span data-ttu-id="2a583-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="2a583-105">Method</span></span>|<span data-ttu-id="2a583-106">説明</span><span class="sxs-lookup"><span data-stu-id="2a583-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2a583-107">GetRegisters メソッド</span><span class="sxs-lookup"><span data-stu-id="2a583-107">GetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregisters-method.md)|<span data-ttu-id="2a583-108">ビットマスクによって指定された、(現在コードを実行しているコンピューター上の) 各レジスタの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="2a583-108">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>|  
|[<span data-ttu-id="2a583-109">GetRegistersAvailable メソッド</span><span class="sxs-lookup"><span data-stu-id="2a583-109">GetRegistersAvailable Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md)|<span data-ttu-id="2a583-110">現在使用できるレジスタ`ICorDebugRegisterSet`を示すビットマスクを取得します。</span><span class="sxs-lookup"><span data-stu-id="2a583-110">Gets a bit mask indicating which registers in this `ICorDebugRegisterSet` are currently available.</span></span>|  
|[<span data-ttu-id="2a583-111">GetThreadContext メソッド</span><span class="sxs-lookup"><span data-stu-id="2a583-111">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getthreadcontext-method.md)|<span data-ttu-id="2a583-112">現在のスレッドのコンテキストを取得します。</span><span class="sxs-lookup"><span data-stu-id="2a583-112">Gets the context of the current thread.</span></span>|  
|[<span data-ttu-id="2a583-113">SetRegisters メソッド</span><span class="sxs-lookup"><span data-stu-id="2a583-113">SetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-setregisters-method.md)|<span data-ttu-id="2a583-114">.NET Framework バージョン2.0 には実装されていません。</span><span class="sxs-lookup"><span data-stu-id="2a583-114">Not implemented for the .NET Framework version 2.0.</span></span>|  
|[<span data-ttu-id="2a583-115">SetThreadContext メソッド</span><span class="sxs-lookup"><span data-stu-id="2a583-115">SetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-setthreadcontext-method.md)|<span data-ttu-id="2a583-116">.NET Framework 2.0 には実装されていません。</span><span class="sxs-lookup"><span data-stu-id="2a583-116">Not implemented for the .NET Framework 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2a583-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="2a583-117">Remarks</span></span>  
 <span data-ttu-id="2a583-118">インターフェイス`ICorDebugRegisterSet`では、32ビットレジスタのみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="2a583-118">The `ICorDebugRegisterSet` interface supports only 32-bit registers.</span></span> <span data-ttu-id="2a583-119">追加のレジスタを必要とする IA-64 などのプラットフォームで[ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)インターフェイスを使用します。</span><span class="sxs-lookup"><span data-stu-id="2a583-119">Use the [ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md) interface on platforms such as IA-64 that require additional registers.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2a583-120">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="2a583-120">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a583-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="2a583-121">Requirements</span></span>  
 <span data-ttu-id="2a583-122">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a583-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a583-123">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="2a583-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2a583-124">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="2a583-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2a583-125">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a583-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a583-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="2a583-126">See also</span></span>

- [<span data-ttu-id="2a583-127">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2a583-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="2a583-128">ICorDebugRegisterSet2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2a583-128">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
