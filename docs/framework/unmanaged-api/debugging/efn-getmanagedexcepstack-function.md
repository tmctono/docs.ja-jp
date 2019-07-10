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
ms.openlocfilehash: 61f4e057a487462feb385ca0e3ca977fdd165f56
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739096"
---
# <a name="efngetmanagedexcepstack-function"></a><span data-ttu-id="76bd4-102">\_EFN\_GetManagedExcepStack 関数</span><span class="sxs-lookup"><span data-stu-id="76bd4-102">\_EFN\_GetManagedExcepStack Function</span></span>
<span data-ttu-id="76bd4-103">指定したマネージド例外オブジェクトのアドレスに応じて、中に含まれているスタック トレースの文字列バージョンを返します。</span><span class="sxs-lookup"><span data-stu-id="76bd4-103">Given a managed exception object address, returns a string version of the stack trace contained inside.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76bd4-104">構文</span><span class="sxs-lookup"><span data-stu-id="76bd4-104">Syntax</span></span>  
  
```cpp  
HRESULT _EFN_GetManagedExcepStack(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       StackObjAddr,  
    [out] __out_ecount(cbString) PSTR szStackString,  
    [out] ULONG         cbString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="76bd4-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="76bd4-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="76bd4-106">[in]デバッグ中のクライアント。</span><span class="sxs-lookup"><span data-stu-id="76bd4-106">[in] The client being debugged.</span></span>  
  
 `StackObjAddr`  
 <span data-ttu-id="76bd4-107">[in]派生したマネージ オブジェクトのポインター<xref:System.Exception>します。</span><span class="sxs-lookup"><span data-stu-id="76bd4-107">[in] A managed object pointer, derived from <xref:System.Exception>.</span></span>  
  
 <span data-ttu-id="76bd4-108">szStackString</span><span class="sxs-lookup"><span data-stu-id="76bd4-108">szStackString</span></span>  
 <span data-ttu-id="76bd4-109">[out]返される文字列。</span><span class="sxs-lookup"><span data-stu-id="76bd4-109">[out] The returned string.</span></span>  
  
 `cbString`  
 <span data-ttu-id="76bd4-110">[out]文字列のバッファーで使用できる文字数。</span><span class="sxs-lookup"><span data-stu-id="76bd4-110">[out] The number of characters available in the string buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="76bd4-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="76bd4-111">Remarks</span></span>  
 <span data-ttu-id="76bd4-112">ないマネージ コードのスレッドで現在のコンテキストの場合、関数は、0xa0 の施設の値と 0x1000 のエラー コードをマネージを返します。</span><span class="sxs-lookup"><span data-stu-id="76bd4-112">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76bd4-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="76bd4-113">Requirements</span></span>  
 <span data-ttu-id="76bd4-114">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="76bd4-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76bd4-115">**ヘッダー:** SOS_Stacktrace.h</span><span class="sxs-lookup"><span data-stu-id="76bd4-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="76bd4-116">**.NET framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76bd4-116">**.NET Framework Version:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76bd4-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="76bd4-117">See also</span></span>

- [<span data-ttu-id="76bd4-118">デバッグ グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="76bd4-118">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
