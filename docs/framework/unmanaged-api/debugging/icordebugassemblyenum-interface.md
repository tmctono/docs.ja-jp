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
ms.openlocfilehash: 988637956b1176235618bf8f4aee7ecec9ce1187
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894832"
---
# <a name="icordebugassemblyenum-interface"></a><span data-ttu-id="937af-102">ICorDebugAssemblyEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="937af-102">ICorDebugAssemblyEnum Interface</span></span>

<span data-ttu-id="937af-103">ICorDebugEnum メソッドを実装し、アセンブリ配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="937af-103">Implements ICorDebugEnum methods and enumerates ICorDebugAssembly arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="937af-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="937af-104">Methods</span></span>  
  
|<span data-ttu-id="937af-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="937af-105">Method</span></span>|<span data-ttu-id="937af-106">説明</span><span class="sxs-lookup"><span data-stu-id="937af-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="937af-107">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="937af-107">Next Method</span></span>](icordebugassemblyenum-next-method.md)|<span data-ttu-id="937af-108">現在の`ICorDebugAssembly`位置から開始して、列挙内の指定した数のインスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="937af-108">Gets the specified number of `ICorDebugAssembly` instances in the enumeration, starting from the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="937af-109">解説</span><span class="sxs-lookup"><span data-stu-id="937af-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="937af-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="937af-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="937af-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="937af-111">Requirements</span></span>  
 <span data-ttu-id="937af-112">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="937af-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="937af-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="937af-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="937af-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="937af-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="937af-115">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="937af-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="937af-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="937af-116">See also</span></span>

- [<span data-ttu-id="937af-117">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="937af-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
