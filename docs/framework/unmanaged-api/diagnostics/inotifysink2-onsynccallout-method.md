---
title: INotifySink2::OnSyncCallOut メソッド
ms.date: 03/30/2017
api_name:
- INotifySink2.OnSyncCallOut
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallOut
helpviewer_keywords:
- INotifySink2::OnSyncCallOut method [.NET Framework debugging]
- OnSyncCallOut method [.NET Framework debugging]
ms.assetid: 97f15656-8677-4079-8553-a1d8603355d6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f4cea67587e4a33b4b9f8cbaa23cb7d299004a46
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736164"
---
# <a name="inotifysink2onsynccallout-method"></a><span data-ttu-id="c8081-102">INotifySink2::OnSyncCallOut メソッド</span><span class="sxs-lookup"><span data-stu-id="c8081-102">INotifySink2::OnSyncCallOut Method</span></span>
<span data-ttu-id="c8081-103">呼び出しがないときに呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="c8081-103">Gets invoked when a call is out.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8081-104">構文</span><span class="sxs-lookup"><span data-stu-id="c8081-104">Syntax</span></span>  
  
```cpp  
HRESULT OnSyncCallOut  
(  
    [in]  CALL_ID  in_CallID,  
    [out, size_is(, *out_pBufferSize)] BYTE**  out_ppBuffer,  
    [out] DWORD*   out_pBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c8081-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c8081-105">Parameters</span></span>  
 `in_CallID`  
 <span data-ttu-id="c8081-106">[in]呼び出しの ID。参照してください[CALL_ID 構造体](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md)します。</span><span class="sxs-lookup"><span data-stu-id="c8081-106">[in] ID of the call that is out. See [CALL_ID Structure](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span></span>  
  
 `out_ppBuffer`  
 <span data-ttu-id="c8081-107">[out]バッファーを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="c8081-107">[out] Call buffer.</span></span>  
  
 `out_pBufferSize`  
 <span data-ttu-id="c8081-108">[out]呼び出しバッファーのバイト単位のサイズ。</span><span class="sxs-lookup"><span data-stu-id="c8081-108">[out] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c8081-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="c8081-109">Return Value</span></span>  
 <span data-ttu-id="c8081-110">メソッドが成功した場合は s_ok を返します。</span><span class="sxs-lookup"><span data-stu-id="c8081-110">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8081-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="c8081-111">Requirements</span></span>  
 <span data-ttu-id="c8081-112">**ヘッダー:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="c8081-112">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8081-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="c8081-113">See also</span></span>

- [<span data-ttu-id="c8081-114">INotifySink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c8081-114">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [<span data-ttu-id="c8081-115">INotifySource2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c8081-115">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [<span data-ttu-id="c8081-116">INotifyConnection2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c8081-116">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
