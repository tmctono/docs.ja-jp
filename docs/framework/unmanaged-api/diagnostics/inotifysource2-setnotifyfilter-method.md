---
title: INotifySource2::SetNotifyFilter メソッド
ms.date: 03/30/2017
api_name:
- INotifySource2.SetNotifyFilter
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySource2::SetNotifyFilter
helpviewer_keywords:
- INotifySource2::SetNotifyFilter method [.NET Framework debugging]
- SetNotifyFilter method [.NET Framework debugging]
ms.assetid: 6351fc92-b126-4af6-9bf3-0a8ce92845fc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: abe1c8881330ebba5f7b68452cf3db0666ac20c3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736230"
---
# <a name="inotifysource2setnotifyfilter-method"></a><span data-ttu-id="f0e05-102">INotifySource2::SetNotifyFilter メソッド</span><span class="sxs-lookup"><span data-stu-id="f0e05-102">INotifySource2::SetNotifyFilter Method</span></span>
<span data-ttu-id="f0e05-103">このソースで使用するための通知フィルターが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="f0e05-103">Assigns a notification filter for use with this source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0e05-104">構文</span><span class="sxs-lookup"><span data-stu-id="f0e05-104">Syntax</span></span>  
  
```cpp  
HRESULT SetNotifyFilter  
(  
    [in]  NOTIFY_FILTER   in_NotifyFilter,  
    [in]  USER_THREAD*    in_pUserThreadFilter  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0e05-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f0e05-105">Parameters</span></span>  
 `in_NotifyFilter`  
 <span data-ttu-id="f0e05-106">[in]ビットごとの組み合わせ、 [NOTIFY_FILTER](../../../../docs/framework/unmanaged-api/diagnostics/notify-filter-enumeration.md)デバッガー API のコールバックを識別する列挙値。</span><span class="sxs-lookup"><span data-stu-id="f0e05-106">[in] A bitwise combination of the [NOTIFY_FILTER](../../../../docs/framework/unmanaged-api/diagnostics/notify-filter-enumeration.md) enumeration values that identify callbacks for the debugger API.</span></span>  
  
 `in_pUserThreadFilter`  
 <span data-ttu-id="f0e05-107">[in]ポインターを[USER_THREAD](../../../../docs/framework/unmanaged-api/diagnostics/user-thread-structure.md) API にデバッガー スレッドを識別する構造体。</span><span class="sxs-lookup"><span data-stu-id="f0e05-107">[in] A pointer to a [USER_THREAD](../../../../docs/framework/unmanaged-api/diagnostics/user-thread-structure.md) structure that identifies threads for the debugger API.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f0e05-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="f0e05-108">Return Value</span></span>  
 <span data-ttu-id="f0e05-109">メソッドが成功した場合は s_ok を返します。</span><span class="sxs-lookup"><span data-stu-id="f0e05-109">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0e05-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="f0e05-110">Requirements</span></span>  
 <span data-ttu-id="f0e05-111">**ヘッダー:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="f0e05-111">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0e05-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="f0e05-112">See also</span></span>

- [<span data-ttu-id="f0e05-113">INotifySource2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f0e05-113">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [<span data-ttu-id="f0e05-114">INotifyConnection2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f0e05-114">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
- [<span data-ttu-id="f0e05-115">INotifySink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f0e05-115">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
