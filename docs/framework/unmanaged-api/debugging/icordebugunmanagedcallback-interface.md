---
title: ICorDebugUnmanagedCallback インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugUnmanagedCallback
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugUnmanagedCallback
helpviewer_keywords:
- ICorDebugUnmanagedCallback interface [.NET Framework debugging]
ms.assetid: bc71cbca-7d73-40e5-84dd-2109fade3c2a
topic_type:
- apiref
ms.openlocfilehash: dd5baa282d15d121b62b4dc4dd41bcf9ff393570
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "83395879"
---
# <a name="icordebugunmanagedcallback-interface"></a><span data-ttu-id="e12f2-102">ICorDebugUnmanagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e12f2-102">ICorDebugUnmanagedCallback Interface</span></span>
<span data-ttu-id="e12f2-103">共通言語ランタイム (CLR) に直接関連しないネイティブイベントの通知を提供します。</span><span class="sxs-lookup"><span data-stu-id="e12f2-103">Provides notification of native events that are not directly related to the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e12f2-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="e12f2-104">Methods</span></span>  
  
|<span data-ttu-id="e12f2-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="e12f2-105">Method</span></span>|<span data-ttu-id="e12f2-106">説明</span><span class="sxs-lookup"><span data-stu-id="e12f2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e12f2-107">DebugEvent メソッド</span><span class="sxs-lookup"><span data-stu-id="e12f2-107">DebugEvent Method</span></span>](icordebugunmanagedcallback-debugevent-method.md)|<span data-ttu-id="e12f2-108">ネイティブイベントが発生したことをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="e12f2-108">Notifies the debugger that a native event has been fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e12f2-109">解説</span><span class="sxs-lookup"><span data-stu-id="e12f2-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e12f2-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="e12f2-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e12f2-111">要件</span><span class="sxs-lookup"><span data-stu-id="e12f2-111">Requirements</span></span>  
 <span data-ttu-id="e12f2-112">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e12f2-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e12f2-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e12f2-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e12f2-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e12f2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e12f2-115">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e12f2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e12f2-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="e12f2-116">See also</span></span>

- [<span data-ttu-id="e12f2-117">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="e12f2-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
