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
ms.openlocfilehash: 826736d2db7aa1e618a2e5fe0655cedad9556b17
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213440"
---
# <a name="icordebugprocess3-interface"></a><span data-ttu-id="fd2d2-102">ICorDebugProcess3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fd2d2-102">ICorDebugProcess3 Interface</span></span>
<span data-ttu-id="fd2d2-103">カスタムのデバッガー通知を制御します。</span><span class="sxs-lookup"><span data-stu-id="fd2d2-103">Controls custom debugger notifications.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fd2d2-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="fd2d2-104">Methods</span></span>  
  
|<span data-ttu-id="fd2d2-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="fd2d2-105">Method</span></span>|<span data-ttu-id="fd2d2-106">説明</span><span class="sxs-lookup"><span data-stu-id="fd2d2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fd2d2-107">SetEnableCustomNotification メソッド</span><span class="sxs-lookup"><span data-stu-id="fd2d2-107">SetEnableCustomNotification Method</span></span>](icordebugprocess3-setenablecustomnotification-method.md)|<span data-ttu-id="fd2d2-108">指定された型のカスタムデバッガー通知を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="fd2d2-108">Enables and disables custom debugger notifications of the specified type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd2d2-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="fd2d2-109">Remarks</span></span>  
 <span data-ttu-id="fd2d2-110">このインターフェイスは、ICorDebugProcess2 インターフェイスとインターフェイスを論理的に拡張します。</span><span class="sxs-lookup"><span data-stu-id="fd2d2-110">This interface logically extends the ICorDebugProcess and ICorDebugProcess2 interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fd2d2-111">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="fd2d2-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd2d2-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="fd2d2-112">Requirements</span></span>  
 <span data-ttu-id="fd2d2-113">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd2d2-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd2d2-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fd2d2-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fd2d2-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fd2d2-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fd2d2-116">**.NET Framework のバージョン:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd2d2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd2d2-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="fd2d2-117">See also</span></span>

- [<span data-ttu-id="fd2d2-118">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="fd2d2-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="fd2d2-119">デバッグ</span><span class="sxs-lookup"><span data-stu-id="fd2d2-119">Debugging</span></span>](index.md)
