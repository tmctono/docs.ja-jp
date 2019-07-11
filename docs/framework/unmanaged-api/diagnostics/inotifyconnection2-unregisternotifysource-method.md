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
ms.openlocfilehash: 7b8a8c3dbfb7b9949811025846484ab233ed3741
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776626"
---
# <a name="inotifyconnection2unregisternotifysource-method"></a><span data-ttu-id="3aae1-102">INotifyConnection2::UnregisterNotifySource メソッド</span><span class="sxs-lookup"><span data-stu-id="3aae1-102">INotifyConnection2::UnregisterNotifySource Method</span></span>
<span data-ttu-id="3aae1-103">接続から、指定された通知のソース オブジェクトを削除します。</span><span class="sxs-lookup"><span data-stu-id="3aae1-103">Removes a specified notification source object from the connection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3aae1-104">構文</span><span class="sxs-lookup"><span data-stu-id="3aae1-104">Syntax</span></span>  
  
```cpp  
HRESULT UnregisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3aae1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3aae1-105">Parameters</span></span>  
 `in_pNotifySource`  
 <span data-ttu-id="3aae1-106">[in]通知登録を解除するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="3aae1-106">[in] Notification object to be unregistered.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3aae1-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="3aae1-107">Return Value</span></span>  
 <span data-ttu-id="3aae1-108">メソッドが成功した場合は s_ok を返します。</span><span class="sxs-lookup"><span data-stu-id="3aae1-108">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3aae1-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="3aae1-109">Requirements</span></span>  
 <span data-ttu-id="3aae1-110">**ヘッダー:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="3aae1-110">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3aae1-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="3aae1-111">See also</span></span>

- [<span data-ttu-id="3aae1-112">INotifyConnection2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3aae1-112">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
- [<span data-ttu-id="3aae1-113">INotifySource2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3aae1-113">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [<span data-ttu-id="3aae1-114">INotifySink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3aae1-114">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [<span data-ttu-id="3aae1-115">RegisterNotifySource メソッド</span><span class="sxs-lookup"><span data-stu-id="3aae1-115">RegisterNotifySource Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-registernotifysource-method.md)
