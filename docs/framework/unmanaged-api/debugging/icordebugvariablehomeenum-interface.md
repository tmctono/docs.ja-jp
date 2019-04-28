---
title: ICorDebugVariableHomeEnum インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHomeEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHomeEnum
helpviewer_keywords:
- ICorDebugVariableHomeEnum interface [.NET Framework debugging]
ms.assetid: c312ae6d-c8dc-48d6-9f1e-ead515c88fdf
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4e67e4685320f56a4a6a8be2e3eb2e6c8065ce59
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769006"
---
# <a name="icordebugvariablehomeenum-interface"></a><span data-ttu-id="61373-102">ICorDebugVariableHomeEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="61373-102">ICorDebugVariableHomeEnum Interface</span></span>
<span data-ttu-id="61373-103">ローカル変数と関数の引数、列挙子を提供します。</span><span class="sxs-lookup"><span data-stu-id="61373-103">Provides an enumerator to the local variables and arguments in a function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="61373-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="61373-104">Methods</span></span>  
  
|<span data-ttu-id="61373-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="61373-105">Method</span></span>|<span data-ttu-id="61373-106">説明</span><span class="sxs-lookup"><span data-stu-id="61373-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="61373-107">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="61373-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md)|<span data-ttu-id="61373-108">指定した数を取得[ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)については、ローカル変数と関数の引数を格納するインスタンス。</span><span class="sxs-lookup"><span data-stu-id="61373-108">Gets the specified number of [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instances that contain information about the local variables and arguments in a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="61373-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="61373-109">Remarks</span></span>  
 <span data-ttu-id="61373-110">`ICorDebugVariableHomeEnum` ICorDebugEnum インターフェイスを実装するインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="61373-110">The `ICorDebugVariableHomeEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="61373-111">`ICorDebugVariableHomeEnum`インスタンスには、 [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)インスタンスを呼び出すことによって、 [ICorDebugCode4::EnumerateVariableHomes](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-enumeratevariablehomes-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="61373-111">An `ICorDebugVariableHomeEnum` instance is populated with [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instances by calling the [ICorDebugCode4::EnumerateVariableHomes](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-enumeratevariablehomes-method.md) method.</span></span> <span data-ttu-id="61373-112">各[ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)コレクション内のインスタンスがローカル変数または関数の引数を表します。</span><span class="sxs-lookup"><span data-stu-id="61373-112">Each [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instance in the collection represents a local variable or argument in a function.</span></span> <span data-ttu-id="61373-113">[ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)呼び出すことによって、コレクション内のオブジェクトを列挙することができます、 [ICorDebugVariableHomeEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="61373-113">The  [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) objects in the collection can be enumerated by calling the [ICorDebugVariableHomeEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61373-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="61373-114">Requirements</span></span>  
 <span data-ttu-id="61373-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="61373-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61373-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="61373-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="61373-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="61373-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="61373-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61373-118">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61373-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="61373-119">See also</span></span>

- [<span data-ttu-id="61373-120">ICorDebugVariableHome インターフェイス</span><span class="sxs-lookup"><span data-stu-id="61373-120">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
- [<span data-ttu-id="61373-121">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="61373-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
