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
ms.openlocfilehash: c7afe074afb9b38d6fefa1192799120dbb50b403
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442060"
---
# <a name="inotifysink2-interface"></a><span data-ttu-id="38dfd-102">INotifySink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="38dfd-102">INotifySink2 Interface</span></span>
<span data-ttu-id="38dfd-103">シンク通知のメソッドを宣言します。</span><span class="sxs-lookup"><span data-stu-id="38dfd-103">Declares methods for sink notification.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="38dfd-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="38dfd-104">Methods</span></span>  
  
|<span data-ttu-id="38dfd-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="38dfd-105">Method</span></span>|<span data-ttu-id="38dfd-106">説明</span><span class="sxs-lookup"><span data-stu-id="38dfd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="38dfd-107">OnSyncCallEnter メソッド</span><span class="sxs-lookup"><span data-stu-id="38dfd-107">OnSyncCallEnter Method</span></span>](inotifysink2-onsynccallenter-method.md)|<span data-ttu-id="38dfd-108">呼び出しを入力したときに呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="38dfd-108">Gets invoked when entering a call.</span></span>|  
|[<span data-ttu-id="38dfd-109">OnSyncCallExit メソッド</span><span class="sxs-lookup"><span data-stu-id="38dfd-109">OnSyncCallExit Method</span></span>](inotifysink2-onsynccallexit-method.md)|<span data-ttu-id="38dfd-110">呼び出しを終了したときに呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="38dfd-110">Gets invoked when exiting a call.</span></span>|  
|[<span data-ttu-id="38dfd-111">OnSyncCallOut メソッド</span><span class="sxs-lookup"><span data-stu-id="38dfd-111">OnSyncCallOut Method</span></span>](inotifysink2-onsynccallout-method.md)|<span data-ttu-id="38dfd-112">呼び出しがタイムアウトしたときに呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="38dfd-112">Gets invoked when a call is out.</span></span>|  
|[<span data-ttu-id="38dfd-113">OnSyncCallReturn メソッド</span><span class="sxs-lookup"><span data-stu-id="38dfd-113">OnSyncCallReturn Method</span></span>](inotifysink2-onsynccallreturn-method.md)|<span data-ttu-id="38dfd-114">呼び出しから制御が戻ったときに呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="38dfd-114">Gets invoked when a call returns.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="38dfd-115">要件</span><span class="sxs-lookup"><span data-stu-id="38dfd-115">Requirements</span></span>  
 <span data-ttu-id="38dfd-116">**ヘッダー:** ProtocolNotify2</span><span class="sxs-lookup"><span data-stu-id="38dfd-116">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38dfd-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="38dfd-117">See also</span></span>

- [<span data-ttu-id="38dfd-118">INotifyConnection2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="38dfd-118">INotifyConnection2 Interface</span></span>](inotifyconnection2-interface.md)
- [<span data-ttu-id="38dfd-119">INotifySource2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="38dfd-119">INotifySource2 Interface</span></span>](inotifysource2-interface.md)
- [<span data-ttu-id="38dfd-120">シンボル ストア診断インターフェイス</span><span class="sxs-lookup"><span data-stu-id="38dfd-120">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
