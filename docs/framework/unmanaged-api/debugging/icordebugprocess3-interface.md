---
title: ICorDebugProcess3 インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugProcess3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess3
helpviewer_keywords:
- ICorDebugProcess3 interface [.NET Framework debugging]
ms.assetid: ced9c82e-d7b0-4806-a151-98b6611d3097
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 05900f55885f8f3a4c470d6842c42d0fc3e0171e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957455"
---
# <a name="icordebugprocess3-interface"></a><span data-ttu-id="ab421-102">ICorDebugProcess3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ab421-102">ICorDebugProcess3 Interface</span></span>
<span data-ttu-id="ab421-103">カスタムのデバッガー通知を制御します。</span><span class="sxs-lookup"><span data-stu-id="ab421-103">Controls custom debugger notifications.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ab421-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="ab421-104">Methods</span></span>  
  
|<span data-ttu-id="ab421-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="ab421-105">Method</span></span>|<span data-ttu-id="ab421-106">説明</span><span class="sxs-lookup"><span data-stu-id="ab421-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ab421-107">SetEnableCustomNotification メソッド</span><span class="sxs-lookup"><span data-stu-id="ab421-107">SetEnableCustomNotification Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-setenablecustomnotification-method.md)|<span data-ttu-id="ab421-108">指定された型のカスタムデバッガー通知を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="ab421-108">Enables and disables custom debugger notifications of the specified type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ab421-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="ab421-109">Remarks</span></span>  
 <span data-ttu-id="ab421-110">このインターフェイスは、ICorDebugProcess2 インターフェイスとインターフェイスを論理的に拡張します。</span><span class="sxs-lookup"><span data-stu-id="ab421-110">This interface logically extends the ICorDebugProcess and ICorDebugProcess2 interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ab421-111">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="ab421-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab421-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="ab421-112">Requirements</span></span>  
 <span data-ttu-id="ab421-113">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab421-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab421-114">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="ab421-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ab421-115">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="ab421-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ab421-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab421-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab421-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="ab421-117">See also</span></span>

- [<span data-ttu-id="ab421-118">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ab421-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="ab421-119">デバッグ</span><span class="sxs-lookup"><span data-stu-id="ab421-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
