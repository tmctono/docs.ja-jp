---
title: _EFN_GetManagedObjectName 関数
ms.date: 03/30/2017
api_name:
- _EFN_GetManagedObjectName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_GetManagedObjectName
helpviewer_keywords:
- _EFN_GetManagedObjectName function [.NET Framework debugging]
ms.assetid: 6e7c6bee-7ced-495f-bf6c-2a5f0c716f7e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4a95008d98436161ac919ef307273bc797519f15
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698344"
---
# <a name="efngetmanagedobjectname-function"></a><span data-ttu-id="7bd7f-102">_EFN_GetManagedObjectName 関数</span><span class="sxs-lookup"><span data-stu-id="7bd7f-102">_EFN_GetManagedObjectName Function</span></span>
<span data-ttu-id="7bd7f-103">指定されたマネージ オブジェクトへのポインターを使用して型の名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="7bd7f-103">Gets the name of a type using the provided managed object pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bd7f-104">構文</span><span class="sxs-lookup"><span data-stu-id="7bd7f-104">Syntax</span></span>  
  
```  
HRESULT _EFN_GetManagedObjectName(  
    [in]  PDEBUG_CLIENT  Client,  
    [in]  ULONG64        objAddr,  
    [out] __out_ecount(cbName) PSTR szName,  
    [out] ULONG          cbName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7bd7f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7bd7f-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="7bd7f-106">[in]デバッグ クライアントへのポインター。</span><span class="sxs-lookup"><span data-stu-id="7bd7f-106">[in] A pointer to the debug client.</span></span>  
  
 `objAddr`  
 <span data-ttu-id="7bd7f-107">[in]マネージ オブジェクトのポインター。</span><span class="sxs-lookup"><span data-stu-id="7bd7f-107">[in] A managed object pointer.</span></span>  
  
 <span data-ttu-id="7bd7f-108">szName</span><span class="sxs-lookup"><span data-stu-id="7bd7f-108">szName</span></span>  
 <span data-ttu-id="7bd7f-109">[out]型の名前。</span><span class="sxs-lookup"><span data-stu-id="7bd7f-109">[out] The name of the type.</span></span>  
  
 `cbName`  
 <span data-ttu-id="7bd7f-110">[out]文字列のバッファーで使用できる文字数。</span><span class="sxs-lookup"><span data-stu-id="7bd7f-110">[out] The number of characters available in the string buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7bd7f-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="7bd7f-111">Remarks</span></span>  
 <span data-ttu-id="7bd7f-112">ないマネージ コードのスレッドで現在のコンテキストの場合、関数は、0xa0 の施設の値と 0x1000 のエラー コードをマネージを返します。</span><span class="sxs-lookup"><span data-stu-id="7bd7f-112">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7bd7f-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="7bd7f-113">Requirements</span></span>  
 <span data-ttu-id="7bd7f-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7bd7f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7bd7f-115">**ヘッダー:** SOS_Stacktrace.h</span><span class="sxs-lookup"><span data-stu-id="7bd7f-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="7bd7f-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7bd7f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bd7f-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="7bd7f-117">See also</span></span>

- [<span data-ttu-id="7bd7f-118">デバッグ グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="7bd7f-118">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
