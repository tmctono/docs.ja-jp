---
title: ICorDebugBreakpointEnum インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpointEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpointEnum
helpviewer_keywords:
- ICorDebugBreakpointEnum interface [.NET Framework debugging]
ms.assetid: 4c6f4f6e-52cc-402e-881b-7b8526544c90
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7fd42f13f699b0b79fd69311186f2b2ca0c9998a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645307"
---
# <a name="icordebugbreakpointenum-interface"></a><span data-ttu-id="f96b0-102">ICorDebugBreakpointEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f96b0-102">ICorDebugBreakpointEnum Interface</span></span>

<span data-ttu-id="f96b0-103">ICorDebugEnum のメソッドを実装し、ICorDebugBreakpoint 配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="f96b0-103">Implements ICorDebugEnum methods, and enumerates ICorDebugBreakpoint arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f96b0-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="f96b0-104">Methods</span></span>  
  
|<span data-ttu-id="f96b0-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="f96b0-105">Method</span></span>|<span data-ttu-id="f96b0-106">説明</span><span class="sxs-lookup"><span data-stu-id="f96b0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f96b0-107">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="f96b0-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpointenum-next-method.md)|<span data-ttu-id="f96b0-108">指定した数を取得`ICorDebugBreakpoint`列挙体の現在位置からのインスタンス。</span><span class="sxs-lookup"><span data-stu-id="f96b0-108">Gets the specified number of `ICorDebugBreakpoint` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f96b0-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="f96b0-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f96b0-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="f96b0-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f96b0-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="f96b0-111">Requirements</span></span>  
 <span data-ttu-id="f96b0-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f96b0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f96b0-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f96b0-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f96b0-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f96b0-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f96b0-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f96b0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f96b0-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="f96b0-116">See also</span></span>

- [<span data-ttu-id="f96b0-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f96b0-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
