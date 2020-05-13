---
title: ICorDebugProcessEnum インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugProcessEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcessEnum
helpviewer_keywords:
- ICorDebugProcessEnum interface [.NET Framework debugging]
ms.assetid: b63a507a-ca97-4be0-8e4f-401cce2125f6
topic_type:
- apiref
ms.openlocfilehash: 3a820381f1c4605d620d74a5915c3e08de69d9fb
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210112"
---
# <a name="icordebugprocessenum-interface"></a><span data-ttu-id="b1cfc-102">ICorDebugProcessEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b1cfc-102">ICorDebugProcessEnum Interface</span></span>
<span data-ttu-id="b1cfc-103">ICorDebugEnum メソッドを実装し、を処理する配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="b1cfc-103">Implements ICorDebugEnum methods and enumerates ICorDebugProcess arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b1cfc-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="b1cfc-104">Methods</span></span>  
  
|<span data-ttu-id="b1cfc-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="b1cfc-105">Method</span></span>|<span data-ttu-id="b1cfc-106">説明</span><span class="sxs-lookup"><span data-stu-id="b1cfc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b1cfc-107">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="b1cfc-107">Next Method</span></span>](icordebugprocessenum-next-method.md)|<span data-ttu-id="b1cfc-108">現在の位置から開始して、指定した数の `ICorDebugProcess` インスタンスを列挙から取得します。</span><span class="sxs-lookup"><span data-stu-id="b1cfc-108">Gets the specified number of `ICorDebugProcess` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b1cfc-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="b1cfc-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b1cfc-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="b1cfc-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1cfc-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="b1cfc-111">Requirements</span></span>  
 <span data-ttu-id="b1cfc-112">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1cfc-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1cfc-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b1cfc-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b1cfc-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b1cfc-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b1cfc-115">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1cfc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1cfc-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="b1cfc-116">See also</span></span>

- [<span data-ttu-id="b1cfc-117">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="b1cfc-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
