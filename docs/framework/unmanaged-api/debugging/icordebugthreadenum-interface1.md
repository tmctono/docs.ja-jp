---
title: ICorDebugThreadEnum インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugThreadEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThreadEnum
helpviewer_keywords:
- ICorDebugThreadEnum interface [.NET Framework debugging]
ms.assetid: 796de687-7dd4-4b7b-a10b-8bf22dc7779f
topic_type:
- apiref
ms.openlocfilehash: 82a7689bb1848d89f5dee4482d8dc7685c9c5b5c
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378332"
---
# <a name="icordebugthreadenum-interface"></a><span data-ttu-id="901ed-102">ICorDebugThreadEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="901ed-102">ICorDebugThreadEnum Interface</span></span>
<span data-ttu-id="901ed-103">ICorDebugEnum メソッドを実装し、の各スレッド配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="901ed-103">Implements ICorDebugEnum methods and enumerates ICorDebugThread arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="901ed-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="901ed-104">Methods</span></span>  
  
|<span data-ttu-id="901ed-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="901ed-105">Method</span></span>|<span data-ttu-id="901ed-106">説明</span><span class="sxs-lookup"><span data-stu-id="901ed-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="901ed-107">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="901ed-107">Next Method</span></span>](icordebugthreadenum-next-method.md)|<span data-ttu-id="901ed-108">現在の位置から開始して、指定した数の `ICorDebugThread` インスタンスを列挙から取得します。</span><span class="sxs-lookup"><span data-stu-id="901ed-108">Gets the specified number of `ICorDebugThread` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="901ed-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="901ed-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="901ed-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="901ed-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="901ed-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="901ed-111">Requirements</span></span>  
 <span data-ttu-id="901ed-112">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="901ed-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="901ed-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="901ed-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="901ed-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="901ed-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="901ed-115">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="901ed-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="901ed-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="901ed-116">See also</span></span>

- [<span data-ttu-id="901ed-117">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="901ed-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
