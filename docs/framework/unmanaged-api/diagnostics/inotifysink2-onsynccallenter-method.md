---
title: INotifySink2::OnSyncCallEnter メソッド
ms.date: 03/30/2017
api_name:
- INotifySink2.OnSyncCallEnter
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallEnter
helpviewer_keywords:
- INotifySink2::OnSyncCallEnter method [.NET Framework debugging]
- OnSyncCallEnter method [.NET Framework debugging]
ms.assetid: e33265be-c25d-4145-ad02-c3e89d6f26c1
topic_type:
- apiref
ms.openlocfilehash: 85f00698f42f120b209cca14f293a58ae4c65f6f
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442034"
---
# <a name="inotifysink2onsynccallenter-method"></a><span data-ttu-id="5e067-102">INotifySink2::OnSyncCallEnter メソッド</span><span class="sxs-lookup"><span data-stu-id="5e067-102">INotifySink2::OnSyncCallEnter Method</span></span>
<span data-ttu-id="5e067-103">呼び出しを入力したときに呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="5e067-103">Gets invoked when entering a call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e067-104">構文</span><span class="sxs-lookup"><span data-stu-id="5e067-104">Syntax</span></span>  
  
```cpp  
HRESULT OnSyncCallEnter  
(  
    [in]  CALL_ID   in_CallID,  
    [in, size_is(in_BufferSize)] BYTE*  in_pBuffer,  
    [in]  DWORD     in_BufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5e067-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5e067-105">Parameters</span></span>  
 `in_CallID`  
 <span data-ttu-id="5e067-106">から入力されている呼び出しの ID。</span><span class="sxs-lookup"><span data-stu-id="5e067-106">[in] ID of the call being entered.</span></span> <span data-ttu-id="5e067-107">「 [CALL_ID 構造](call-id-structure.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e067-107">See [CALL_ID Structure](call-id-structure.md).</span></span>  
  
 `in_pBuffer`  
 <span data-ttu-id="5e067-108">から呼び出しバッファー。</span><span class="sxs-lookup"><span data-stu-id="5e067-108">[in] Call buffer.</span></span>  
  
 `in_BufferSize`  
 <span data-ttu-id="5e067-109">から呼び出しバッファーのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="5e067-109">[in] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5e067-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="5e067-110">Return Value</span></span>  
 <span data-ttu-id="5e067-111">メソッドが成功した場合は S_OK します。</span><span class="sxs-lookup"><span data-stu-id="5e067-111">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e067-112">要件</span><span class="sxs-lookup"><span data-stu-id="5e067-112">Requirements</span></span>  
 <span data-ttu-id="5e067-113">**ヘッダー:** ProtocolNotify2</span><span class="sxs-lookup"><span data-stu-id="5e067-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e067-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="5e067-114">See also</span></span>

- [<span data-ttu-id="5e067-115">INotifySink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5e067-115">INotifySink2 Interface</span></span>](inotifysink2-interface.md)
- [<span data-ttu-id="5e067-116">INotifySource2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5e067-116">INotifySource2 Interface</span></span>](inotifysource2-interface.md)
- [<span data-ttu-id="5e067-117">INotifyConnection2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5e067-117">INotifyConnection2 Interface</span></span>](inotifyconnection2-interface.md)
