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
ms.openlocfilehash: 1893f1f08d727606fecda7669719760179bb76f9
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76778057"
---
# <a name="icordebugassemblyenum-interface"></a><span data-ttu-id="b396e-102">ICorDebugAssemblyEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b396e-102">ICorDebugAssemblyEnum Interface</span></span>

<span data-ttu-id="b396e-103">ICorDebugEnum メソッドを実装し、アセンブリ配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="b396e-103">Implements ICorDebugEnum methods and enumerates ICorDebugAssembly arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b396e-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="b396e-104">Methods</span></span>  
  
|<span data-ttu-id="b396e-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="b396e-105">Method</span></span>|<span data-ttu-id="b396e-106">説明</span><span class="sxs-lookup"><span data-stu-id="b396e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b396e-107">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="b396e-107">Next Method</span></span>](icordebugassemblyenum-next-method.md)|<span data-ttu-id="b396e-108">現在の位置から開始して、列挙内の指定した数の `ICorDebugAssembly` インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="b396e-108">Gets the specified number of `ICorDebugAssembly` instances in the enumeration, starting from the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b396e-109">コメント</span><span class="sxs-lookup"><span data-stu-id="b396e-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b396e-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="b396e-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b396e-111">要件</span><span class="sxs-lookup"><span data-stu-id="b396e-111">Requirements</span></span>  
 <span data-ttu-id="b396e-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b396e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b396e-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b396e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b396e-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b396e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b396e-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b396e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b396e-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="b396e-116">See also</span></span>

- [<span data-ttu-id="b396e-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b396e-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
