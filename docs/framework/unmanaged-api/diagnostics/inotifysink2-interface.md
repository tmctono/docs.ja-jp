---
title: INotifySink2 インターフェイス
ms.date: 03/30/2017
api_name:
- INotifySink2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2
helpviewer_keywords:
- INotifySink2 interface [.NET Framework debugging]
ms.assetid: c1018789-4206-455d-aacc-2d876fc0d0bb
topic_type:
- apiref
ms.openlocfilehash: af50c82974b779b901135795f37e3bd4c8b8c156
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440977"
---
# <a name="inotifysink2-interface"></a><span data-ttu-id="1abe9-102">INotifySink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1abe9-102">INotifySink2 Interface</span></span>
<span data-ttu-id="1abe9-103">シンク通知のメソッドを宣言します。</span><span class="sxs-lookup"><span data-stu-id="1abe9-103">Declares methods for sink notification.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1abe9-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="1abe9-104">Methods</span></span>  
  
|<span data-ttu-id="1abe9-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="1abe9-105">Method</span></span>|<span data-ttu-id="1abe9-106">説明</span><span class="sxs-lookup"><span data-stu-id="1abe9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1abe9-107">OnSyncCallEnter メソッド</span><span class="sxs-lookup"><span data-stu-id="1abe9-107">OnSyncCallEnter Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallenter-method.md)|<span data-ttu-id="1abe9-108">呼び出しを入力したときに呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="1abe9-108">Gets invoked when entering a call.</span></span>|  
|[<span data-ttu-id="1abe9-109">OnSyncCallExit メソッド</span><span class="sxs-lookup"><span data-stu-id="1abe9-109">OnSyncCallExit Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallexit-method.md)|<span data-ttu-id="1abe9-110">呼び出しを終了したときに呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="1abe9-110">Gets invoked when exiting a call.</span></span>|  
|[<span data-ttu-id="1abe9-111">OnSyncCallOut メソッド</span><span class="sxs-lookup"><span data-stu-id="1abe9-111">OnSyncCallOut Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallout-method.md)|<span data-ttu-id="1abe9-112">呼び出しがタイムアウトしたときに呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="1abe9-112">Gets invoked when a call is out.</span></span>|  
|[<span data-ttu-id="1abe9-113">OnSyncCallReturn メソッド</span><span class="sxs-lookup"><span data-stu-id="1abe9-113">OnSyncCallReturn Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallreturn-method.md)|<span data-ttu-id="1abe9-114">呼び出しから制御が戻ったときに呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="1abe9-114">Gets invoked when a call returns.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1abe9-115">要件</span><span class="sxs-lookup"><span data-stu-id="1abe9-115">Requirements</span></span>  
 <span data-ttu-id="1abe9-116">**ヘッダー:** ProtocolNotify2</span><span class="sxs-lookup"><span data-stu-id="1abe9-116">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1abe9-117">参照</span><span class="sxs-lookup"><span data-stu-id="1abe9-117">See also</span></span>

- [<span data-ttu-id="1abe9-118">INotifyConnection2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1abe9-118">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
- [<span data-ttu-id="1abe9-119">INotifySource2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1abe9-119">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [<span data-ttu-id="1abe9-120">シンボル ストア診断インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1abe9-120">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
