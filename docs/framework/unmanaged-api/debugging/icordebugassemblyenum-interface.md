---
title: ICorDebugAssemblyEnum インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugAssemblyEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssemblyEnum
helpviewer_keywords:
- ICorDebugAssemblyEnum interface [.NET Framework debugging]
ms.assetid: 891ceb43-5161-421e-a0bf-299962fd7efd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b259ceb8af61785bc77536d2718bdfbb3683c066
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "56979893"
---
# <a name="icordebugassemblyenum-interface"></a><span data-ttu-id="aaa96-102">ICorDebugAssemblyEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="aaa96-102">ICorDebugAssemblyEnum Interface</span></span>

<span data-ttu-id="aaa96-103">ICorDebugEnum メソッドを実装し、ICorDebugAssembly 配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="aaa96-103">Implements ICorDebugEnum methods and enumerates ICorDebugAssembly arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="aaa96-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="aaa96-104">Methods</span></span>  
  
|<span data-ttu-id="aaa96-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="aaa96-105">Method</span></span>|<span data-ttu-id="aaa96-106">説明</span><span class="sxs-lookup"><span data-stu-id="aaa96-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="aaa96-107">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="aaa96-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassemblyenum-next-method.md)|<span data-ttu-id="aaa96-108">指定した数を取得`ICorDebugAssembly`現在位置から、列挙体のインスタンス。</span><span class="sxs-lookup"><span data-stu-id="aaa96-108">Gets the specified number of `ICorDebugAssembly` instances in the enumeration, starting from the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aaa96-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="aaa96-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aaa96-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="aaa96-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aaa96-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="aaa96-111">Requirements</span></span>  
 <span data-ttu-id="aaa96-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="aaa96-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aaa96-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="aaa96-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="aaa96-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aaa96-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aaa96-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aaa96-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aaa96-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="aaa96-116">See also</span></span>
- [<span data-ttu-id="aaa96-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="aaa96-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
