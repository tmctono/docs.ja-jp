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
ms.openlocfilehash: 6980b78dc416e03df578756b7a2ee45a48a4fd5a
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967140"
---
# <a name="icordebugassembly2-interface"></a><span data-ttu-id="7c0b0-102">ICorDebugAssembly2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7c0b0-102">ICorDebugAssembly2 Interface</span></span>

<span data-ttu-id="7c0b0-103">アセンブリを表します。</span><span class="sxs-lookup"><span data-stu-id="7c0b0-103">Represents an assembly.</span></span> <span data-ttu-id="7c0b0-104">このインターフェイスは、ICorDebugAssembly インターフェイスの拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="7c0b0-104">This interface is an extension of the ICorDebugAssembly interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7c0b0-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="7c0b0-105">Methods</span></span>  
  
|<span data-ttu-id="7c0b0-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="7c0b0-106">Method</span></span>|<span data-ttu-id="7c0b0-107">説明</span><span class="sxs-lookup"><span data-stu-id="7c0b0-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7c0b0-108">IsFullyTrusted メソッド</span><span class="sxs-lookup"><span data-stu-id="7c0b0-108">IsFullyTrusted Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly2-isfullytrusted-method.md)|<span data-ttu-id="7c0b0-109">かどうか、アセンブリで許可されている完全な信頼ランタイムのセキュリティ システムを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="7c0b0-109">Gets a value that indicates whether the assembly has been granted full trust by the runtime security system.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c0b0-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="7c0b0-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7c0b0-111">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="7c0b0-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c0b0-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="7c0b0-112">Requirements</span></span>  
 <span data-ttu-id="7c0b0-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c0b0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c0b0-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7c0b0-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7c0b0-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c0b0-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7c0b0-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c0b0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c0b0-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="7c0b0-117">See also</span></span>
- [<span data-ttu-id="7c0b0-118">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7c0b0-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
