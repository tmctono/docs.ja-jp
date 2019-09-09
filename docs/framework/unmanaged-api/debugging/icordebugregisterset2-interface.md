---
title: ICorDebugRegisterSet2 インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2
helpviewer_keywords:
- ICorDebugRegisterSet2 interface [.NET Framework debugging]
ms.assetid: d7fbccbf-3b6b-4db8-a96d-768e1cb6b1a6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 95e8ad1ddce57252b7af3c7d72e8f8eb7bdb76b0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69935091"
---
# <a name="icordebugregisterset2-interface"></a><span data-ttu-id="4877d-102">ICorDebugRegisterSet2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4877d-102">ICorDebugRegisterSet2 Interface</span></span>
<span data-ttu-id="4877d-103">64を超えるレジスタを持つハードウェアプラットフォームに対し[て、の](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)機能を拡張します。</span><span class="sxs-lookup"><span data-stu-id="4877d-103">Extends the capabilities of the [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) interface for hardware platforms that have more than 64 registers.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4877d-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="4877d-104">Methods</span></span>  
  
|<span data-ttu-id="4877d-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="4877d-105">Method</span></span>|<span data-ttu-id="4877d-106">説明</span><span class="sxs-lookup"><span data-stu-id="4877d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4877d-107">GetRegisters メソッド</span><span class="sxs-lookup"><span data-stu-id="4877d-107">GetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-getregisters-method.md)|<span data-ttu-id="4877d-108">ビットマスクによって指定された、(現在コードを実行しているコンピューター上の) 各レジスタの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="4877d-108">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>|  
|[<span data-ttu-id="4877d-109">GetRegistersAvailable メソッド</span><span class="sxs-lookup"><span data-stu-id="4877d-109">GetRegistersAvailable Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-getregistersavailable-method.md)|<span data-ttu-id="4877d-110">使用できるレジスタのビットマップを提供するバイト配列を取得します。</span><span class="sxs-lookup"><span data-stu-id="4877d-110">Gets an array of bytes that provides a bitmap of the available registers.</span></span>|  
|[<span data-ttu-id="4877d-111">SetRegisters メソッド</span><span class="sxs-lookup"><span data-stu-id="4877d-111">SetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-setregisters-method.md)|<span data-ttu-id="4877d-112">.NET Framework バージョン2.0 では実装されていません。</span><span class="sxs-lookup"><span data-stu-id="4877d-112">Not implemented in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4877d-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="4877d-113">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4877d-114">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="4877d-114">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4877d-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="4877d-115">Requirements</span></span>  
 <span data-ttu-id="4877d-116">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4877d-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4877d-117">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="4877d-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4877d-118">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="4877d-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4877d-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4877d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4877d-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="4877d-120">See also</span></span>

- [<span data-ttu-id="4877d-121">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4877d-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="4877d-122">ICorDebugRegisterSet インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4877d-122">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
