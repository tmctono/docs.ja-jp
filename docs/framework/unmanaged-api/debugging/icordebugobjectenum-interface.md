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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0144539987f14bed83bfc9eab2f5ca26d2a609ae
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61942390"
---
# <a name="icordebugobjectenum-interface"></a><span data-ttu-id="af021-102">ICorDebugObjectEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="af021-102">ICorDebugObjectEnum Interface</span></span>

<span data-ttu-id="af021-103">ICorDebugEnum のメソッドを実装し、相対仮想アドレス (Rva) でオブジェクトの配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="af021-103">Implements ICorDebugEnum methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="af021-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="af021-104">Methods</span></span>  
  
|<span data-ttu-id="af021-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="af021-105">Method</span></span>|<span data-ttu-id="af021-106">説明</span><span class="sxs-lookup"><span data-stu-id="af021-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="af021-107">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="af021-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectenum-next-method.md)|<span data-ttu-id="af021-108">列挙体の現在位置から指定した数のオブジェクトの Rva を取得します。</span><span class="sxs-lookup"><span data-stu-id="af021-108">Gets the RVAs of the specified number of objects from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af021-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="af021-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="af021-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="af021-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af021-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="af021-111">Requirements</span></span>  
 <span data-ttu-id="af021-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="af021-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af021-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="af021-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="af021-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="af021-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="af021-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af021-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af021-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="af021-116">See also</span></span>

- [<span data-ttu-id="af021-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="af021-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
