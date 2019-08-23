---
title: ICorDebugModuleBreakpoint インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugModuleBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleBreakpoint
helpviewer_keywords:
- ICorDebugModuleBreakpoint interface [.NET Framework debugging]
ms.assetid: 34667162-f314-475f-ae1b-ce9cb0fcbb83
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 03616f2756830e180155102492b15e18fee1085c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965124"
---
# <a name="icordebugmodulebreakpoint-interface"></a><span data-ttu-id="74e96-102">ICorDebugModuleBreakpoint インターフェイス</span><span class="sxs-lookup"><span data-stu-id="74e96-102">ICorDebugModuleBreakpoint Interface</span></span>

<span data-ttu-id="74e96-103">特定のモジュールへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="74e96-103">Provides access to specific modules.</span></span> <span data-ttu-id="74e96-104">このインターフェイスは、ICorDebugBreakpoint インターフェイスのサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="74e96-104">This interface is a subclass of the ICorDebugBreakpoint interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="74e96-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="74e96-105">Methods</span></span>  
  
|<span data-ttu-id="74e96-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="74e96-106">Method</span></span>|<span data-ttu-id="74e96-107">説明</span><span class="sxs-lookup"><span data-stu-id="74e96-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="74e96-108">GetModule メソッド</span><span class="sxs-lookup"><span data-stu-id="74e96-108">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodulebreakpoint-getmodule-method.md)|<span data-ttu-id="74e96-109">このブレークポイントが設定されているモジュールを参照するモジュールへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="74e96-109">Gets an interface pointer to an ICorDebugModule that references the module where this breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="74e96-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="74e96-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="74e96-111">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="74e96-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74e96-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="74e96-112">Requirements</span></span>  
 <span data-ttu-id="74e96-113">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="74e96-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74e96-114">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="74e96-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="74e96-115">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="74e96-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="74e96-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74e96-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74e96-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="74e96-117">See also</span></span>

- [<span data-ttu-id="74e96-118">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="74e96-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
