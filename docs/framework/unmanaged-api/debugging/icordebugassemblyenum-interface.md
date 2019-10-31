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
ms.openlocfilehash: aa0bc34c3cb3ac330582cee0843022e913376fc2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192159"
---
# <a name="icordebugassemblyenum-interface"></a><span data-ttu-id="09e03-102">ICorDebugAssemblyEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="09e03-102">ICorDebugAssemblyEnum Interface</span></span>

<span data-ttu-id="09e03-103">ICorDebugEnum メソッドを実装し、アセンブリ配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="09e03-103">Implements ICorDebugEnum methods and enumerates ICorDebugAssembly arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="09e03-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="09e03-104">Methods</span></span>  
  
|<span data-ttu-id="09e03-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="09e03-105">Method</span></span>|<span data-ttu-id="09e03-106">説明</span><span class="sxs-lookup"><span data-stu-id="09e03-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="09e03-107">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="09e03-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassemblyenum-next-method.md)|<span data-ttu-id="09e03-108">現在の位置から開始して、列挙内の指定した数の `ICorDebugAssembly` インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="09e03-108">Gets the specified number of `ICorDebugAssembly` instances in the enumeration, starting from the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="09e03-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="09e03-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="09e03-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="09e03-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09e03-111">［要件］</span><span class="sxs-lookup"><span data-stu-id="09e03-111">Requirements</span></span>  
 <span data-ttu-id="09e03-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09e03-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09e03-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="09e03-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="09e03-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="09e03-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="09e03-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09e03-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09e03-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="09e03-116">See also</span></span>

- [<span data-ttu-id="09e03-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="09e03-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
