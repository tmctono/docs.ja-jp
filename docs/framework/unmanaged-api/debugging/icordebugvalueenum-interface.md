---
title: ICorDebugValueEnum インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugValueEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueEnum
helpviewer_keywords:
- ICorDebugValueEnum interface [.NET Framework debugging]
ms.assetid: 88989482-a09f-4bd0-9adb-16f47b0291fd
topic_type:
- apiref
ms.openlocfilehash: 5f95202bd0c8c5045c10378068ae83cad3d93fdd
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396463"
---
# <a name="icordebugvalueenum-interface"></a><span data-ttu-id="13fbf-102">ICorDebugValueEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="13fbf-102">ICorDebugValueEnum Interface</span></span>
<span data-ttu-id="13fbf-103">"ICorDebugEnum" メソッドを実装し、"ICorDebugValue" 配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="13fbf-103">Implements "ICorDebugEnum" methods and enumerates "ICorDebugValue" arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="13fbf-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="13fbf-104">Methods</span></span>  
  
|<span data-ttu-id="13fbf-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="13fbf-105">Method</span></span>|<span data-ttu-id="13fbf-106">説明</span><span class="sxs-lookup"><span data-stu-id="13fbf-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="13fbf-107">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="13fbf-107">Next Method</span></span>](icordebugvalueenum-next-method.md)|<span data-ttu-id="13fbf-108">現在の位置から開始して、指定した数の `ICorDebugValue` インスタンスを列挙から取得します。</span><span class="sxs-lookup"><span data-stu-id="13fbf-108">Gets the specified number of `ICorDebugValue` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="13fbf-109">解説</span><span class="sxs-lookup"><span data-stu-id="13fbf-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="13fbf-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="13fbf-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13fbf-111">要件</span><span class="sxs-lookup"><span data-stu-id="13fbf-111">Requirements</span></span>  
 <span data-ttu-id="13fbf-112">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13fbf-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13fbf-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="13fbf-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="13fbf-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="13fbf-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="13fbf-115">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13fbf-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13fbf-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="13fbf-116">See also</span></span>

- [<span data-ttu-id="13fbf-117">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="13fbf-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
