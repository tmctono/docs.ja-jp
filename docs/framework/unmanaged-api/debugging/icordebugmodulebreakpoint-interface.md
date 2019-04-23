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
ms.openlocfilehash: d6a43a264fcaa94ce4e629d8db504e9d416f6b89
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59179713"
---
# <a name="icordebugmodulebreakpoint-interface"></a><span data-ttu-id="b6444-102">ICorDebugModuleBreakpoint インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b6444-102">ICorDebugModuleBreakpoint Interface</span></span>

<span data-ttu-id="b6444-103">特定のモジュールへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="b6444-103">Provides access to specific modules.</span></span> <span data-ttu-id="b6444-104">このインターフェイスは、ICorDebugBreakpoint インターフェイスのサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="b6444-104">This interface is a subclass of the ICorDebugBreakpoint interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b6444-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="b6444-105">Methods</span></span>  
  
|<span data-ttu-id="b6444-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="b6444-106">Method</span></span>|<span data-ttu-id="b6444-107">説明</span><span class="sxs-lookup"><span data-stu-id="b6444-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b6444-108">GetModule メソッド</span><span class="sxs-lookup"><span data-stu-id="b6444-108">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodulebreakpoint-getmodule-method.md)|<span data-ttu-id="b6444-109">このブレークポイントが設定されているモジュールを参照する、ICorDebugModule にインターフェイス ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="b6444-109">Gets an interface pointer to an ICorDebugModule that references the module where this breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b6444-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="b6444-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b6444-111">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="b6444-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6444-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="b6444-112">Requirements</span></span>  
 <span data-ttu-id="b6444-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6444-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6444-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b6444-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b6444-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b6444-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b6444-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6444-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6444-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="b6444-117">See also</span></span>

- [<span data-ttu-id="b6444-118">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b6444-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
