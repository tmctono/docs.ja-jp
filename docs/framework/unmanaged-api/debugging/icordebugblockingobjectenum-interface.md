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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59161461"
---
# <a name="icordebugblockingobjectenum-interface"></a><span data-ttu-id="3b624-102">ICorDebugBlockingObjectEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3b624-102">ICorDebugBlockingObjectEnum Interface</span></span>
<span data-ttu-id="3b624-103">一覧については、列挙子を提供します。 [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)構造体。</span><span class="sxs-lookup"><span data-stu-id="3b624-103">Provides an enumerator for a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span> <span data-ttu-id="3b624-104">このインターフェイスは、ICorDebugEnum インターフェイスのサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="3b624-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3b624-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="3b624-105">Methods</span></span>  
  
|<span data-ttu-id="3b624-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="3b624-106">Method</span></span>|<span data-ttu-id="3b624-107">説明</span><span class="sxs-lookup"><span data-stu-id="3b624-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3b624-108">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="3b624-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-next-method.md)|<span data-ttu-id="3b624-109">一覧を列挙します[CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)構造体。</span><span class="sxs-lookup"><span data-stu-id="3b624-109">Enumerates through a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3b624-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="3b624-110">Remarks</span></span>  
 <span data-ttu-id="3b624-111">各 `CorDebugBlockingObject` 構造体は、スレッドをブロックしているオブジェクトを表します。</span><span class="sxs-lookup"><span data-stu-id="3b624-111">Each `CorDebugBlockingObject` structure represents an object that is blocking a thread.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3b624-112">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="3b624-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b624-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="3b624-113">Requirements</span></span>  
 <span data-ttu-id="3b624-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b624-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b624-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3b624-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3b624-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3b624-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="3b624-117">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="3b624-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3b624-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="3b624-118">See also</span></span>

- [<span data-ttu-id="3b624-119">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="3b624-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="3b624-120">デバッグ</span><span class="sxs-lookup"><span data-stu-id="3b624-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
