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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b46c74ec0bfc1fc44bcaca07439c472b0fd8393f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59113764"
---
# <a name="icordebugilframe3-interface"></a><span data-ttu-id="00f18-102">ICorDebugILFrame3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="00f18-102">ICorDebugILFrame3 Interface</span></span>
<span data-ttu-id="00f18-103">関数の戻り値をカプセル化するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="00f18-103">Provides a method that encapsulates the return value of a function.</span></span> `ICorDebugILFrame3` <span data-ttu-id="00f18-104">ICorDebugILFrame および ICorDebugILFrame2 インターフェイスの論理的な拡張です。</span><span class="sxs-lookup"><span data-stu-id="00f18-104">is a logical extension of the ICorDebugILFrame and ICorDebugILFrame2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="00f18-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="00f18-105">Methods</span></span>  
  
|<span data-ttu-id="00f18-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="00f18-106">Method</span></span>|<span data-ttu-id="00f18-107">説明</span><span class="sxs-lookup"><span data-stu-id="00f18-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="00f18-108">GetReturnValueForILOffset メソッド</span><span class="sxs-lookup"><span data-stu-id="00f18-108">GetReturnValueForILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md)|<span data-ttu-id="00f18-109">関数の戻り値をカプセル化する ICorDebugValue オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="00f18-109">Gets an ICorDebugValue object that encapsulates the return value of a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="00f18-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="00f18-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="00f18-111">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="00f18-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00f18-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="00f18-112">Requirements</span></span>  
 <span data-ttu-id="00f18-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="00f18-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00f18-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="00f18-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="00f18-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="00f18-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="00f18-116">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="00f18-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="00f18-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="00f18-117">See also</span></span>

- [<span data-ttu-id="00f18-118">ICorDebugCode3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="00f18-118">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
- [<span data-ttu-id="00f18-119">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="00f18-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
