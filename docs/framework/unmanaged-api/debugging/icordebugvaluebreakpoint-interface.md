---
title: ICorDebugValueBreakpoint インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugValueBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueBreakpoint
helpviewer_keywords:
- ICorDebugValueBreakpoint interface [.NET Framework debugging]
ms.assetid: c02338fe-da6c-467f-9567-70ebb387e901
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 778359a7d26b6e2f19984a1f7ff06a527f2449f0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59167747"
---
# <a name="icordebugvaluebreakpoint-interface"></a><span data-ttu-id="cf839-102">ICorDebugValueBreakpoint インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cf839-102">ICorDebugValueBreakpoint Interface</span></span>
<span data-ttu-id="cf839-103">特定の値へのアクセスを提供する ICorDebugBreakpoint インターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="cf839-103">Extends the ICorDebugBreakpoint interface to provide access to specific values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cf839-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="cf839-104">Methods</span></span>  
  
|<span data-ttu-id="cf839-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="cf839-105">Method</span></span>|<span data-ttu-id="cf839-106">説明</span><span class="sxs-lookup"><span data-stu-id="cf839-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cf839-107">GetValue メソッド</span><span class="sxs-lookup"><span data-stu-id="cf839-107">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvaluebreakpoint-getvalue-method.md)|<span data-ttu-id="cf839-108">ブレークポイントが設定されているオブジェクトの値を表す ICorDebugValue オブジェクトへのインターフェイス ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="cf839-108">Gets an interface pointer to an ICorDebugValue object that represents the value of the object upon which the breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cf839-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="cf839-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cf839-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="cf839-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf839-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="cf839-111">Requirements</span></span>  
 <span data-ttu-id="cf839-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf839-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf839-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cf839-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cf839-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cf839-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cf839-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf839-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf839-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="cf839-116">See also</span></span>

- [<span data-ttu-id="cf839-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cf839-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
