---
title: ICorDebugBlockingObjectEnum インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugBlockingObjectEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBlockingObjectEnum
helpviewer_keywords:
- ICorDebugBlockingObjectEnum interface [.NET Framework debugging]
ms.assetid: 208e5c2d-3f3f-404e-8b3c-7cccc14ddb16
topic_type:
- apiref
ms.openlocfilehash: bfd61d985eac3ab56d8a5df9474b2b1a9f641f3e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122841"
---
# <a name="icordebugblockingobjectenum-interface"></a><span data-ttu-id="50c6b-102">ICorDebugBlockingObjectEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="50c6b-102">ICorDebugBlockingObjectEnum Interface</span></span>
<span data-ttu-id="50c6b-103">[CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)構造体のリストの列挙子を提供します。</span><span class="sxs-lookup"><span data-stu-id="50c6b-103">Provides an enumerator for a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span> <span data-ttu-id="50c6b-104">このインターフェイスは、ICorDebugEnum インターフェイスのサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="50c6b-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="50c6b-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="50c6b-105">Methods</span></span>  
  
|<span data-ttu-id="50c6b-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="50c6b-106">Method</span></span>|<span data-ttu-id="50c6b-107">説明</span><span class="sxs-lookup"><span data-stu-id="50c6b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="50c6b-108">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="50c6b-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-next-method.md)|<span data-ttu-id="50c6b-109">[CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)構造体のリストを使用して列挙します。</span><span class="sxs-lookup"><span data-stu-id="50c6b-109">Enumerates through a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50c6b-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="50c6b-110">Remarks</span></span>  
 <span data-ttu-id="50c6b-111">各 `CorDebugBlockingObject` 構造体は、スレッドをブロックしているオブジェクトを表します。</span><span class="sxs-lookup"><span data-stu-id="50c6b-111">Each `CorDebugBlockingObject` structure represents an object that is blocking a thread.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="50c6b-112">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="50c6b-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50c6b-113">［要件］</span><span class="sxs-lookup"><span data-stu-id="50c6b-113">Requirements</span></span>  
 <span data-ttu-id="50c6b-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="50c6b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50c6b-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="50c6b-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="50c6b-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="50c6b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="50c6b-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50c6b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50c6b-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="50c6b-118">See also</span></span>

- [<span data-ttu-id="50c6b-119">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="50c6b-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="50c6b-120">デバッグ</span><span class="sxs-lookup"><span data-stu-id="50c6b-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
