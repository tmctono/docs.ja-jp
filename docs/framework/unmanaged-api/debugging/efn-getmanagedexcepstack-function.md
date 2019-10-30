---
title: _EFN_GetManagedExcepStack 関数
ms.date: 03/30/2017
api_name:
- _EFN_GetManagedExcepStack
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_GetManagedExcepStack
helpviewer_keywords:
- _EFN_GetManagedExcepStack function [.NET Framework debugging]
ms.assetid: 21ceed9e-62b2-4024-b027-6d095109955a
topic_type:
- apiref
ms.openlocfilehash: 9bcc03cc97a62b4c1cadacd7c0b2bc46b9fec470
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134142"
---
# <a name="_efn_getmanagedexcepstack-function"></a><span data-ttu-id="f1710-102">\_EFN\_GetManagedExcepStack 関数</span><span class="sxs-lookup"><span data-stu-id="f1710-102">\_EFN\_GetManagedExcepStack Function</span></span>
<span data-ttu-id="f1710-103">指定したマネージド例外オブジェクトのアドレスに応じて、中に含まれているスタック トレースの文字列バージョンを返します。</span><span class="sxs-lookup"><span data-stu-id="f1710-103">Given a managed exception object address, returns a string version of the stack trace contained inside.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1710-104">構文</span><span class="sxs-lookup"><span data-stu-id="f1710-104">Syntax</span></span>  
  
```cpp  
HRESULT _EFN_GetManagedExcepStack(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       StackObjAddr,  
    [out] __out_ecount(cbString) PSTR szStackString,  
    [out] ULONG         cbString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1710-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f1710-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="f1710-106">からデバッグ中のクライアント。</span><span class="sxs-lookup"><span data-stu-id="f1710-106">[in] The client being debugged.</span></span>  
  
 `StackObjAddr`  
 <span data-ttu-id="f1710-107">から<xref:System.Exception>から派生したマネージオブジェクトポインター。</span><span class="sxs-lookup"><span data-stu-id="f1710-107">[in] A managed object pointer, derived from <xref:System.Exception>.</span></span>  
  
 <span data-ttu-id="f1710-108">szStackString</span><span class="sxs-lookup"><span data-stu-id="f1710-108">szStackString</span></span>  
 <span data-ttu-id="f1710-109">入出力返された文字列。</span><span class="sxs-lookup"><span data-stu-id="f1710-109">[out] The returned string.</span></span>  
  
 `cbString`  
 <span data-ttu-id="f1710-110">入出力文字列バッファーで使用できる文字数。</span><span class="sxs-lookup"><span data-stu-id="f1710-110">[out] The number of characters available in the string buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1710-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="f1710-111">Remarks</span></span>  
 <span data-ttu-id="f1710-112">現在コンテキスト内にあるスレッドにマネージコードがない場合、関数は、ファシリティ値が0xa0 で、エラーコードが0x1000 の HRESULT SOS_E_NOMANAGEDCODE を返します。</span><span class="sxs-lookup"><span data-stu-id="f1710-112">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1710-113">［要件］</span><span class="sxs-lookup"><span data-stu-id="f1710-113">Requirements</span></span>  
 <span data-ttu-id="f1710-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1710-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1710-115">**ヘッダー:** SOS_Stacktrace</span><span class="sxs-lookup"><span data-stu-id="f1710-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="f1710-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1710-116">**.NET Framework Version:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1710-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="f1710-117">See also</span></span>

- [<span data-ttu-id="f1710-118">デバッグ グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="f1710-118">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
