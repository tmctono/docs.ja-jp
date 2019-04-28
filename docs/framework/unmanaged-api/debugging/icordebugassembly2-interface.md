---
title: ICorDebugAssembly2 インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly2
helpviewer_keywords:
- ICorDebugAssembly2 interface [.NET Framework debugging]
ms.assetid: c0766e29-e573-4f9a-a928-167d1de5aa7e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 70eac63855f16205c3d5dbcb28305481b986484c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645553"
---
# <a name="icordebugassembly2-interface"></a><span data-ttu-id="aa146-102">ICorDebugAssembly2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="aa146-102">ICorDebugAssembly2 Interface</span></span>

<span data-ttu-id="aa146-103">アセンブリを表します。</span><span class="sxs-lookup"><span data-stu-id="aa146-103">Represents an assembly.</span></span> <span data-ttu-id="aa146-104">このインターフェイスは、ICorDebugAssembly インターフェイスの拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="aa146-104">This interface is an extension of the ICorDebugAssembly interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="aa146-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="aa146-105">Methods</span></span>  
  
|<span data-ttu-id="aa146-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="aa146-106">Method</span></span>|<span data-ttu-id="aa146-107">説明</span><span class="sxs-lookup"><span data-stu-id="aa146-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="aa146-108">IsFullyTrusted メソッド</span><span class="sxs-lookup"><span data-stu-id="aa146-108">IsFullyTrusted Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly2-isfullytrusted-method.md)|<span data-ttu-id="aa146-109">かどうか、アセンブリで許可されている完全な信頼ランタイムのセキュリティ システムを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="aa146-109">Gets a value that indicates whether the assembly has been granted full trust by the runtime security system.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aa146-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="aa146-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aa146-111">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="aa146-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa146-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="aa146-112">Requirements</span></span>  
 <span data-ttu-id="aa146-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa146-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa146-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="aa146-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="aa146-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aa146-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aa146-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa146-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa146-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="aa146-117">See also</span></span>

- [<span data-ttu-id="aa146-118">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="aa146-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
