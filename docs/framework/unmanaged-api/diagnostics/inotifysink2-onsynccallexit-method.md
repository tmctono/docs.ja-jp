---
title: INotifySink2::OnSyncCallExit メソッド
ms.date: 03/30/2017
api_name:
- INotifySink2.OnSyncCallExit
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallExit
helpviewer_keywords:
- INotifySink2::OnSyncCallExit method [.NET Framework debugging]
- OnSyncCallExit method [.NET Framework debugging]
ms.assetid: d9d7600e-a8f5-443a-96de-67d26e130f2d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9144ab7fc74bdb5b980b4ff1e1a903653bd056f6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59216276"
---
# <a name="inotifysink2onsynccallexit-method"></a><span data-ttu-id="31847-102">INotifySink2::OnSyncCallExit メソッド</span><span class="sxs-lookup"><span data-stu-id="31847-102">INotifySink2::OnSyncCallExit Method</span></span>
<span data-ttu-id="31847-103">呼び出しが終了するときに呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="31847-103">Gets invoked when exiting a call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31847-104">構文</span><span class="sxs-lookup"><span data-stu-id="31847-104">Syntax</span></span>  
  
```  
HRESULT OnSyncCallExit  
(  
    [in]  CALL_ID   in_CallID,  
    [out, size_is(, *out_pBufferSize)] BYTE**  out_ppBuffer,  
    [out] DWORD*    out_pBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="31847-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="31847-105">Parameters</span></span>  
 `in_CallID`  
 <span data-ttu-id="31847-106">[in]終了する呼び出しの ID。</span><span class="sxs-lookup"><span data-stu-id="31847-106">[in] ID of the call being exited.</span></span> <span data-ttu-id="31847-107">参照してください[CALL_ID 構造体](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md)します。</span><span class="sxs-lookup"><span data-stu-id="31847-107">See [CALL_ID Structure](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span></span>  
  
 `out_ppBuffer`  
 <span data-ttu-id="31847-108">[out]バッファーを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="31847-108">[out] Call buffer.</span></span>  
  
 `out_pBufferSize`  
 <span data-ttu-id="31847-109">[out]呼び出しバッファーのバイト単位のサイズ。</span><span class="sxs-lookup"><span data-stu-id="31847-109">[out] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="31847-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="31847-110">Return Value</span></span>  
 <span data-ttu-id="31847-111">メソッドが成功した場合は s_ok を返します。</span><span class="sxs-lookup"><span data-stu-id="31847-111">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31847-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="31847-112">Requirements</span></span>  
 <span data-ttu-id="31847-113">**ヘッダー:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="31847-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31847-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="31847-114">See also</span></span>

- [<span data-ttu-id="31847-115">INotifySink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="31847-115">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [<span data-ttu-id="31847-116">INotifySource2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="31847-116">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [<span data-ttu-id="31847-117">INotifyConnection2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="31847-117">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
