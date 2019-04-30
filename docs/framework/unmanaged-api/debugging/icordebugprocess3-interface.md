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
ms.openlocfilehash: 0ccc45482f691d9950c641ef126a657052a280e8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987702"
---
# <a name="icordebugprocess3-interface"></a><span data-ttu-id="749a9-102">ICorDebugProcess3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="749a9-102">ICorDebugProcess3 Interface</span></span>
<span data-ttu-id="749a9-103">カスタムのデバッガー通知を制御します。</span><span class="sxs-lookup"><span data-stu-id="749a9-103">Controls custom debugger notifications.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="749a9-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="749a9-104">Methods</span></span>  
  
|<span data-ttu-id="749a9-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="749a9-105">Method</span></span>|<span data-ttu-id="749a9-106">説明</span><span class="sxs-lookup"><span data-stu-id="749a9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="749a9-107">SetEnableCustomNotification メソッド</span><span class="sxs-lookup"><span data-stu-id="749a9-107">SetEnableCustomNotification Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-setenablecustomnotification-method.md)|<span data-ttu-id="749a9-108">有効にし、指定した型のカスタムのデバッガー通知を無効にします。</span><span class="sxs-lookup"><span data-stu-id="749a9-108">Enables and disables custom debugger notifications of the specified type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="749a9-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="749a9-109">Remarks</span></span>  
 <span data-ttu-id="749a9-110">このインターフェイスは、ICorDebugProcess および ICorDebugProcess2 インターフェイスを論理的に拡張します。</span><span class="sxs-lookup"><span data-stu-id="749a9-110">This interface logically extends the ICorDebugProcess and ICorDebugProcess2 interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="749a9-111">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="749a9-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="749a9-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="749a9-112">Requirements</span></span>  
 <span data-ttu-id="749a9-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="749a9-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="749a9-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="749a9-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="749a9-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="749a9-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="749a9-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="749a9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="749a9-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="749a9-117">See also</span></span>

- [<span data-ttu-id="749a9-118">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="749a9-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="749a9-119">デバッグ</span><span class="sxs-lookup"><span data-stu-id="749a9-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
