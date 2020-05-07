---
title: ICLRDataTarget::GetCurrentThreadID メソッド
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetCurrentThreadID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetCurrentThreadID
helpviewer_keywords:
- GetCurrentThreadID method, ICLRDataTarget interface [.NET Framework debugging]
- ICLRDataTarget::GetCurrentThreadID method [.NET Framework debugging]
ms.assetid: dc9a0a6c-d592-4fb7-86ed-62684da3b0e1
topic_type:
- apiref
ms.openlocfilehash: c75c55b64ff20728bc5695d0ddfe1b4f6deda4a6
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860643"
---
# <a name="iclrdatatargetgetcurrentthreadid-method"></a><span data-ttu-id="437fb-102">ICLRDataTarget::GetCurrentThreadID メソッド</span><span class="sxs-lookup"><span data-stu-id="437fb-102">ICLRDataTarget::GetCurrentThreadID Method</span></span>
<span data-ttu-id="437fb-103">現在のスレッドのオペレーティングシステム id を取得します。</span><span class="sxs-lookup"><span data-stu-id="437fb-103">Gets the operating system identifier for the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="437fb-104">構文</span><span class="sxs-lookup"><span data-stu-id="437fb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentThreadID (  
    [out] ULONG32    *threadID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="437fb-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="437fb-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="437fb-106">入出力ターゲットプロセスの現在のスレッドのオペレーティングシステム識別子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="437fb-106">[out] A pointer to the operating system identifier of the current thread for the target process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="437fb-107">解説</span><span class="sxs-lookup"><span data-stu-id="437fb-107">Remarks</span></span>  
 <span data-ttu-id="437fb-108">ターゲットプロセスの現在のスレッドが存在しない場合、 `GetCurrentThreadID`メソッドは失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="437fb-108">If there is no current thread for the target process, the `GetCurrentThreadID` method may fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="437fb-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="437fb-109">Requirements</span></span>  
 <span data-ttu-id="437fb-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="437fb-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="437fb-111">**ヘッダー:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="437fb-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="437fb-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="437fb-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="437fb-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="437fb-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="437fb-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="437fb-114">See also</span></span>

- [<span data-ttu-id="437fb-115">ICLRDataTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="437fb-115">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
