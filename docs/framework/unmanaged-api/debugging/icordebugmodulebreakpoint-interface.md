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
ms.openlocfilehash: df3ad3fa4ef4eeee7e23ca1629da7a8b8ce09711
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792925"
---
# <a name="icordebugmodulebreakpoint-interface"></a><span data-ttu-id="a751c-102">ICorDebugModuleBreakpoint インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a751c-102">ICorDebugModuleBreakpoint Interface</span></span>

<span data-ttu-id="a751c-103">特定のモジュールへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="a751c-103">Provides access to specific modules.</span></span> <span data-ttu-id="a751c-104">このインターフェイスは、ICorDebugBreakpoint インターフェイスのサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="a751c-104">This interface is a subclass of the ICorDebugBreakpoint interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a751c-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="a751c-105">Methods</span></span>  
  
|<span data-ttu-id="a751c-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="a751c-106">Method</span></span>|<span data-ttu-id="a751c-107">説明</span><span class="sxs-lookup"><span data-stu-id="a751c-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a751c-108">GetModule メソッド</span><span class="sxs-lookup"><span data-stu-id="a751c-108">GetModule Method</span></span>](icordebugmodulebreakpoint-getmodule-method.md)|<span data-ttu-id="a751c-109">このブレークポイントが設定されているモジュールを参照するモジュールへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="a751c-109">Gets an interface pointer to an ICorDebugModule that references the module where this breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a751c-110">コメント</span><span class="sxs-lookup"><span data-stu-id="a751c-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a751c-111">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="a751c-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a751c-112">要件</span><span class="sxs-lookup"><span data-stu-id="a751c-112">Requirements</span></span>  
 <span data-ttu-id="a751c-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a751c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a751c-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a751c-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a751c-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a751c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a751c-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a751c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a751c-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="a751c-117">See also</span></span>

- [<span data-ttu-id="a751c-118">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a751c-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
