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
ms.openlocfilehash: 22ae1d24040a8ee5000e0ff2fbeb2b45e08050df
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784354"
---
# <a name="icordebugbreakpointenum-interface"></a><span data-ttu-id="cbbde-102">ICorDebugBreakpointEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cbbde-102">ICorDebugBreakpointEnum Interface</span></span>

<span data-ttu-id="cbbde-103">ICorDebugEnum メソッドを実装し、ICorDebugBreakpoint 配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="cbbde-103">Implements ICorDebugEnum methods, and enumerates ICorDebugBreakpoint arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cbbde-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="cbbde-104">Methods</span></span>  
  
|<span data-ttu-id="cbbde-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="cbbde-105">Method</span></span>|<span data-ttu-id="cbbde-106">説明</span><span class="sxs-lookup"><span data-stu-id="cbbde-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cbbde-107">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="cbbde-107">Next Method</span></span>](icordebugbreakpointenum-next-method.md)|<span data-ttu-id="cbbde-108">現在の位置から開始して、指定した数の `ICorDebugBreakpoint` インスタンスを列挙から取得します。</span><span class="sxs-lookup"><span data-stu-id="cbbde-108">Gets the specified number of `ICorDebugBreakpoint` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cbbde-109">コメント</span><span class="sxs-lookup"><span data-stu-id="cbbde-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cbbde-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="cbbde-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cbbde-111">要件</span><span class="sxs-lookup"><span data-stu-id="cbbde-111">Requirements</span></span>  
 <span data-ttu-id="cbbde-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cbbde-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbbde-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cbbde-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cbbde-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cbbde-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cbbde-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cbbde-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbbde-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="cbbde-116">See also</span></span>

- [<span data-ttu-id="cbbde-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cbbde-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
