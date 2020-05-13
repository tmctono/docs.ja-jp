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
ms.openlocfilehash: 7c60fa775b82372b50d1eb3891f107b97df3e73a
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378266"
---
# <a name="icordebugregisterset-interface"></a><span data-ttu-id="cb975-102">ICorDebugRegisterSet インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cb975-102">ICorDebugRegisterSet Interface</span></span>
<span data-ttu-id="cb975-103">現在コードを実行しているコンピューターで使用できるレジスタのセットを表します。</span><span class="sxs-lookup"><span data-stu-id="cb975-103">Represents the set of registers available on the computer that is currently executing code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cb975-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="cb975-104">Methods</span></span>  
  
|<span data-ttu-id="cb975-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="cb975-105">Method</span></span>|<span data-ttu-id="cb975-106">説明</span><span class="sxs-lookup"><span data-stu-id="cb975-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cb975-107">GetRegisters メソッド</span><span class="sxs-lookup"><span data-stu-id="cb975-107">GetRegisters Method</span></span>](icordebugregisterset-getregisters-method.md)|<span data-ttu-id="cb975-108">ビットマスクによって指定された、(現在コードを実行しているコンピューター上の) 各レジスタの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="cb975-108">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>|  
|[<span data-ttu-id="cb975-109">GetRegistersAvailable メソッド</span><span class="sxs-lookup"><span data-stu-id="cb975-109">GetRegistersAvailable Method</span></span>](icordebugregisterset-getregistersavailable-method.md)|<span data-ttu-id="cb975-110">現在使用できるレジスタを示すビットマスクを取得し `ICorDebugRegisterSet` ます。</span><span class="sxs-lookup"><span data-stu-id="cb975-110">Gets a bit mask indicating which registers in this `ICorDebugRegisterSet` are currently available.</span></span>|  
|[<span data-ttu-id="cb975-111">GetThreadContext メソッド</span><span class="sxs-lookup"><span data-stu-id="cb975-111">GetThreadContext Method</span></span>](icordebugregisterset-getthreadcontext-method.md)|<span data-ttu-id="cb975-112">現在のスレッドのコンテキストを取得します。</span><span class="sxs-lookup"><span data-stu-id="cb975-112">Gets the context of the current thread.</span></span>|  
|[<span data-ttu-id="cb975-113">SetRegisters メソッド</span><span class="sxs-lookup"><span data-stu-id="cb975-113">SetRegisters Method</span></span>](icordebugregisterset-setregisters-method.md)|<span data-ttu-id="cb975-114">.NET Framework バージョン2.0 には実装されていません。</span><span class="sxs-lookup"><span data-stu-id="cb975-114">Not implemented for the .NET Framework version 2.0.</span></span>|  
|[<span data-ttu-id="cb975-115">SetThreadContext メソッド</span><span class="sxs-lookup"><span data-stu-id="cb975-115">SetThreadContext Method</span></span>](icordebugregisterset-setthreadcontext-method.md)|<span data-ttu-id="cb975-116">.NET Framework 2.0 には実装されていません。</span><span class="sxs-lookup"><span data-stu-id="cb975-116">Not implemented for the .NET Framework 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cb975-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="cb975-117">Remarks</span></span>  
 <span data-ttu-id="cb975-118">インターフェイスでは、 `ICorDebugRegisterSet` 32 ビットレジスタのみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="cb975-118">The `ICorDebugRegisterSet` interface supports only 32-bit registers.</span></span> <span data-ttu-id="cb975-119">追加のレジスタを必要とする IA-64 などのプラットフォームで[ICorDebugRegisterSet2](icordebugregisterset2-interface.md)インターフェイスを使用します。</span><span class="sxs-lookup"><span data-stu-id="cb975-119">Use the [ICorDebugRegisterSet2](icordebugregisterset2-interface.md) interface on platforms such as IA-64 that require additional registers.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cb975-120">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="cb975-120">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb975-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="cb975-121">Requirements</span></span>  
 <span data-ttu-id="cb975-122">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb975-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb975-123">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cb975-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cb975-124">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cb975-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cb975-125">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb975-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb975-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="cb975-126">See also</span></span>

- [<span data-ttu-id="cb975-127">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="cb975-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="cb975-128">ICorDebugRegisterSet2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cb975-128">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
