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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7e201b9a350c030da59e2b6ed27f84f570c8e621
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59126660"
---
# <a name="efngetmanagedexcepstack-function"></a><span data-ttu-id="287bb-102">_EFN_GetManagedExcepStack 関数</span><span class="sxs-lookup"><span data-stu-id="287bb-102">_EFN_GetManagedExcepStack Function</span></span>
<span data-ttu-id="287bb-103">指定したマネージド例外オブジェクトのアドレスに応じて、中に含まれているスタック トレースの文字列バージョンを返します。</span><span class="sxs-lookup"><span data-stu-id="287bb-103">Given a managed exception object address, returns a string version of the stack trace contained inside.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="287bb-104">構文</span><span class="sxs-lookup"><span data-stu-id="287bb-104">Syntax</span></span>  
  
```  
HRESULT _EFN_GetManagedExcepStack(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       StackObjAddr,  
    [out] __out_ecount(cbString) PSTR szStackString,  
    [out] ULONG         cbString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="287bb-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="287bb-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="287bb-106">[in]デバッグ中のクライアント。</span><span class="sxs-lookup"><span data-stu-id="287bb-106">[in] The client being debugged.</span></span>  
  
 `StackObjAddr`  
 <span data-ttu-id="287bb-107">[in]派生したマネージ オブジェクトのポインター<xref:System.Exception>します。</span><span class="sxs-lookup"><span data-stu-id="287bb-107">[in] A managed object pointer, derived from <xref:System.Exception>.</span></span>  
  
 <span data-ttu-id="287bb-108">szStackString</span><span class="sxs-lookup"><span data-stu-id="287bb-108">szStackString</span></span>  
 <span data-ttu-id="287bb-109">[out]返される文字列。</span><span class="sxs-lookup"><span data-stu-id="287bb-109">[out] The returned string.</span></span>  
  
 `cbString`  
 <span data-ttu-id="287bb-110">[out]文字列のバッファーで使用できる文字数。</span><span class="sxs-lookup"><span data-stu-id="287bb-110">[out] The number of characters available in the string buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="287bb-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="287bb-111">Remarks</span></span>  
 <span data-ttu-id="287bb-112">ないマネージ コードのスレッドで現在のコンテキストの場合、関数は、0xa0 の施設の値と 0x1000 のエラー コードをマネージを返します。</span><span class="sxs-lookup"><span data-stu-id="287bb-112">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="287bb-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="287bb-113">Requirements</span></span>  
 <span data-ttu-id="287bb-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="287bb-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="287bb-115">**ヘッダー:** SOS_Stacktrace.h</span><span class="sxs-lookup"><span data-stu-id="287bb-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="287bb-116">**.NET framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="287bb-116">**.NET Framework Version:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="287bb-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="287bb-117">See also</span></span>

- [<span data-ttu-id="287bb-118">デバッグ グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="287bb-118">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
