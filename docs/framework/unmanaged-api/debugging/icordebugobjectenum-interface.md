---
title: ICorDebugObjectEnum インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugObjectEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectEnum
helpviewer_keywords:
- ICorDebugObjectEnum interface [.NET Framework debugging]
ms.assetid: 9ffb4498-7719-49d3-8890-df2c22248a0c
topic_type:
- apiref
ms.openlocfilehash: 0526c050bcf1316eccf2c756a404fbb971e6d7d0
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792738"
---
# <a name="icordebugobjectenum-interface"></a><span data-ttu-id="72b36-102">ICorDebugObjectEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="72b36-102">ICorDebugObjectEnum Interface</span></span>

<span data-ttu-id="72b36-103">ICorDebugEnum メソッドを実装し、相対仮想アドレス (RVAs) によってオブジェクトの配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="72b36-103">Implements ICorDebugEnum methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="72b36-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="72b36-104">Methods</span></span>  
  
|<span data-ttu-id="72b36-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="72b36-105">Method</span></span>|<span data-ttu-id="72b36-106">説明</span><span class="sxs-lookup"><span data-stu-id="72b36-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="72b36-107">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="72b36-107">Next Method</span></span>](icordebugobjectenum-next-method.md)|<span data-ttu-id="72b36-108">現在の位置から開始して、指定した数のオブジェクトの RVAs を列挙から取得します。</span><span class="sxs-lookup"><span data-stu-id="72b36-108">Gets the RVAs of the specified number of objects from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="72b36-109">コメント</span><span class="sxs-lookup"><span data-stu-id="72b36-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="72b36-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="72b36-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72b36-111">要件</span><span class="sxs-lookup"><span data-stu-id="72b36-111">Requirements</span></span>  
 <span data-ttu-id="72b36-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="72b36-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72b36-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="72b36-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="72b36-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="72b36-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="72b36-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72b36-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72b36-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="72b36-116">See also</span></span>

- [<span data-ttu-id="72b36-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="72b36-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
