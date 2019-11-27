---
title: INotifyConnection2::UnregisterNotifySource メソッド
ms.date: 03/30/2017
api_name:
- INotifyConnection2.UnregisterNotifySource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifyConnection2::UnregisterNotifySource
helpviewer_keywords:
- INotifyConnection2::UnregisterNotifySource method [.NET Framework debugging]
- UnregisterNotifySource method [.NET Framework debugging]
ms.assetid: 2fc6c715-646f-41fd-9c12-c59b40575269
topic_type:
- apiref
ms.openlocfilehash: cf399d0c7dec7528f02988ddfe6ca5c0b1f0c4c3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440985"
---
# <a name="inotifyconnection2unregisternotifysource-method"></a><span data-ttu-id="88243-102">INotifyConnection2::UnregisterNotifySource メソッド</span><span class="sxs-lookup"><span data-stu-id="88243-102">INotifyConnection2::UnregisterNotifySource Method</span></span>
<span data-ttu-id="88243-103">指定された通知ソースオブジェクトを接続から削除します。</span><span class="sxs-lookup"><span data-stu-id="88243-103">Removes a specified notification source object from the connection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88243-104">構文</span><span class="sxs-lookup"><span data-stu-id="88243-104">Syntax</span></span>  
  
```cpp  
HRESULT UnregisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="88243-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="88243-105">Parameters</span></span>  
 `in_pNotifySource`  
 <span data-ttu-id="88243-106">から登録を解除する通知オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="88243-106">[in] Notification object to be unregistered.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="88243-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="88243-107">Return Value</span></span>  
 <span data-ttu-id="88243-108">メソッドが成功した場合は S_OK します。</span><span class="sxs-lookup"><span data-stu-id="88243-108">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88243-109">要件</span><span class="sxs-lookup"><span data-stu-id="88243-109">Requirements</span></span>  
 <span data-ttu-id="88243-110">**ヘッダー:** ProtocolNotify2</span><span class="sxs-lookup"><span data-stu-id="88243-110">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88243-111">参照</span><span class="sxs-lookup"><span data-stu-id="88243-111">See also</span></span>

- [<span data-ttu-id="88243-112">INotifyConnection2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="88243-112">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
- [<span data-ttu-id="88243-113">INotifySource2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="88243-113">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [<span data-ttu-id="88243-114">INotifySink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="88243-114">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [<span data-ttu-id="88243-115">RegisterNotifySource メソッド</span><span class="sxs-lookup"><span data-stu-id="88243-115">RegisterNotifySource Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-registernotifysource-method.md)
