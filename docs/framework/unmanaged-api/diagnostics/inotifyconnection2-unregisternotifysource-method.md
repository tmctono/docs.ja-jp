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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 742be1467d2f1e6eb7d8567ddf85f8e65ea4b8d9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59229460"
---
# <a name="inotifyconnection2unregisternotifysource-method"></a><span data-ttu-id="d582b-102">INotifyConnection2::UnregisterNotifySource メソッド</span><span class="sxs-lookup"><span data-stu-id="d582b-102">INotifyConnection2::UnregisterNotifySource Method</span></span>
<span data-ttu-id="d582b-103">接続から、指定された通知のソース オブジェクトを削除します。</span><span class="sxs-lookup"><span data-stu-id="d582b-103">Removes a specified notification source object from the connection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d582b-104">構文</span><span class="sxs-lookup"><span data-stu-id="d582b-104">Syntax</span></span>  
  
```  
HRESULT UnregisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d582b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d582b-105">Parameters</span></span>  
 `in_pNotifySource`  
 <span data-ttu-id="d582b-106">[in]通知登録を解除するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="d582b-106">[in] Notification object to be unregistered.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d582b-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="d582b-107">Return Value</span></span>  
 <span data-ttu-id="d582b-108">メソッドが成功した場合は s_ok を返します。</span><span class="sxs-lookup"><span data-stu-id="d582b-108">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d582b-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="d582b-109">Requirements</span></span>  
 <span data-ttu-id="d582b-110">**ヘッダー:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="d582b-110">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d582b-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="d582b-111">See also</span></span>

- [<span data-ttu-id="d582b-112">INotifyConnection2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d582b-112">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
- [<span data-ttu-id="d582b-113">INotifySource2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d582b-113">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [<span data-ttu-id="d582b-114">INotifySink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d582b-114">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [<span data-ttu-id="d582b-115">RegisterNotifySource メソッド</span><span class="sxs-lookup"><span data-stu-id="d582b-115">RegisterNotifySource Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-registernotifysource-method.md)
