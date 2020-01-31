---
title: ICorDebugILFrame3 インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame3
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 15212cb5-93d4-4025-bec9-d4b9919eb1fe
topic_type:
- apiref
ms.openlocfilehash: 739c648173d45a9c147ea2a4e469a3a4b518e893
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794335"
---
# <a name="icordebugilframe3-interface"></a><span data-ttu-id="2bb3a-102">ICorDebugILFrame3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2bb3a-102">ICorDebugILFrame3 Interface</span></span>
<span data-ttu-id="2bb3a-103">関数の戻り値をカプセル化するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="2bb3a-103">Provides a method that encapsulates the return value of a function.</span></span> <span data-ttu-id="2bb3a-104">`ICorDebugILFrame3` は、ICorDebugILFrame2 インターフェイスとインターフェイスを論理的に拡張したものです。</span><span class="sxs-lookup"><span data-stu-id="2bb3a-104">`ICorDebugILFrame3` is a logical extension of the ICorDebugILFrame and ICorDebugILFrame2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2bb3a-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="2bb3a-105">Methods</span></span>  
  
|<span data-ttu-id="2bb3a-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="2bb3a-106">Method</span></span>|<span data-ttu-id="2bb3a-107">説明</span><span class="sxs-lookup"><span data-stu-id="2bb3a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2bb3a-108">GetReturnValueForILOffSet メソッド</span><span class="sxs-lookup"><span data-stu-id="2bb3a-108">GetReturnValueForILOffset Method</span></span>](icordebugilframe3-getreturnvalueforiloffset-method.md)|<span data-ttu-id="2bb3a-109">関数の戻り値をカプセル化する ICorDebugValue オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="2bb3a-109">Gets an ICorDebugValue object that encapsulates the return value of a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2bb3a-110">コメント</span><span class="sxs-lookup"><span data-stu-id="2bb3a-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2bb3a-111">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="2bb3a-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bb3a-112">要件</span><span class="sxs-lookup"><span data-stu-id="2bb3a-112">Requirements</span></span>  
 <span data-ttu-id="2bb3a-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2bb3a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2bb3a-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2bb3a-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2bb3a-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2bb3a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2bb3a-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2bb3a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bb3a-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="2bb3a-117">See also</span></span>

- [<span data-ttu-id="2bb3a-118">ICorDebugCode3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2bb3a-118">ICorDebugCode3 Interface</span></span>](icordebugcode3-interface.md)
- [<span data-ttu-id="2bb3a-119">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2bb3a-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
