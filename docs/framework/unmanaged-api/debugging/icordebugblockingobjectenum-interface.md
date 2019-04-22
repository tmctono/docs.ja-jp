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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5a23d21d0ed8c6a6a226d5e58eafb7bde65a4896
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59161461"
---
# <a name="icordebugblockingobjectenum-interface"></a><span data-ttu-id="76f98-102">ICorDebugBlockingObjectEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="76f98-102">ICorDebugBlockingObjectEnum Interface</span></span>
<span data-ttu-id="76f98-103">一覧については、列挙子を提供します。 [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)構造体。</span><span class="sxs-lookup"><span data-stu-id="76f98-103">Provides an enumerator for a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span> <span data-ttu-id="76f98-104">このインターフェイスは、ICorDebugEnum インターフェイスのサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="76f98-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="76f98-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="76f98-105">Methods</span></span>  
  
|<span data-ttu-id="76f98-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="76f98-106">Method</span></span>|<span data-ttu-id="76f98-107">説明</span><span class="sxs-lookup"><span data-stu-id="76f98-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="76f98-108">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="76f98-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-next-method.md)|<span data-ttu-id="76f98-109">一覧を列挙します[CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)構造体。</span><span class="sxs-lookup"><span data-stu-id="76f98-109">Enumerates through a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="76f98-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="76f98-110">Remarks</span></span>  
 <span data-ttu-id="76f98-111">各 `CorDebugBlockingObject` 構造体は、スレッドをブロックしているオブジェクトを表します。</span><span class="sxs-lookup"><span data-stu-id="76f98-111">Each `CorDebugBlockingObject` structure represents an object that is blocking a thread.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="76f98-112">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="76f98-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76f98-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="76f98-113">Requirements</span></span>  
 <span data-ttu-id="76f98-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="76f98-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76f98-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="76f98-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="76f98-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="76f98-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="76f98-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76f98-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76f98-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="76f98-118">See also</span></span>

- [<span data-ttu-id="76f98-119">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="76f98-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="76f98-120">デバッグ</span><span class="sxs-lookup"><span data-stu-id="76f98-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
