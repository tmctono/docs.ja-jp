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
ms.openlocfilehash: 7b0a5d80d984a3c696b178c4d8c936bd47354945
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59135240"
---
# <a name="icordebugregisterset-interface"></a><span data-ttu-id="38fd8-102">ICorDebugRegisterSet インターフェイス</span><span class="sxs-lookup"><span data-stu-id="38fd8-102">ICorDebugRegisterSet Interface</span></span>
<span data-ttu-id="38fd8-103">現在のコードを実行しているコンピューターで使用できるレジスタのセットを表します。</span><span class="sxs-lookup"><span data-stu-id="38fd8-103">Represents the set of registers available on the computer that is currently executing code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="38fd8-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="38fd8-104">Methods</span></span>  
  
|<span data-ttu-id="38fd8-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="38fd8-105">Method</span></span>|<span data-ttu-id="38fd8-106">説明</span><span class="sxs-lookup"><span data-stu-id="38fd8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="38fd8-107">GetRegisters メソッド</span><span class="sxs-lookup"><span data-stu-id="38fd8-107">GetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregisters-method.md)|<span data-ttu-id="38fd8-108">各レジスタの値を取得します (現在のコードを実行しているコンピューター) でビット マスクによって指定されています。</span><span class="sxs-lookup"><span data-stu-id="38fd8-108">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>|  
|[<span data-ttu-id="38fd8-109">GetRegistersAvailable メソッド</span><span class="sxs-lookup"><span data-stu-id="38fd8-109">GetRegistersAvailable Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md)|<span data-ttu-id="38fd8-110">これで登録することを示す取得がビット マスク`ICorDebugRegisterSet`現在利用します。</span><span class="sxs-lookup"><span data-stu-id="38fd8-110">Gets a bit mask indicating which registers in this `ICorDebugRegisterSet` are currently available.</span></span>|  
|[<span data-ttu-id="38fd8-111">GetThreadContext メソッド</span><span class="sxs-lookup"><span data-stu-id="38fd8-111">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getthreadcontext-method.md)|<span data-ttu-id="38fd8-112">現在のスレッドのコンテキストを取得します。</span><span class="sxs-lookup"><span data-stu-id="38fd8-112">Gets the context of the current thread.</span></span>|  
|[<span data-ttu-id="38fd8-113">SetRegisters メソッド</span><span class="sxs-lookup"><span data-stu-id="38fd8-113">SetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-setregisters-method.md)|<span data-ttu-id="38fd8-114">.NET Framework version 2.0 の実装されていません。</span><span class="sxs-lookup"><span data-stu-id="38fd8-114">Not implemented for the .NET Framework version 2.0.</span></span>|  
|[<span data-ttu-id="38fd8-115">SetThreadContext メソッド</span><span class="sxs-lookup"><span data-stu-id="38fd8-115">SetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-setthreadcontext-method.md)|<span data-ttu-id="38fd8-116">.NET Framework 2.0 の実装されていません。</span><span class="sxs-lookup"><span data-stu-id="38fd8-116">Not implemented for the .NET Framework 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="38fd8-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="38fd8-117">Remarks</span></span>  
 <span data-ttu-id="38fd8-118">`ICorDebugRegisterSet`インターフェイスのみの 32 ビット レジスタをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="38fd8-118">The `ICorDebugRegisterSet` interface supports only 32-bit registers.</span></span> <span data-ttu-id="38fd8-119">使用して、 [ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md) IA 64 などの追加のレジスタを必要とするプラットフォーム上のインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="38fd8-119">Use the [ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md) interface on platforms such as IA-64 that require additional registers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="38fd8-120">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="38fd8-120">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38fd8-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="38fd8-121">Requirements</span></span>  
 <span data-ttu-id="38fd8-122">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="38fd8-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38fd8-123">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="38fd8-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="38fd8-124">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="38fd8-124">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="38fd8-125">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="38fd8-125">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="38fd8-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="38fd8-126">See also</span></span>

- [<span data-ttu-id="38fd8-127">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="38fd8-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="38fd8-128">ICorDebugRegisterSet2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="38fd8-128">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
