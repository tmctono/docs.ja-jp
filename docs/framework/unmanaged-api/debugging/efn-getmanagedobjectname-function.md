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
ms.openlocfilehash: 9230e1fcba7c0492e50773e7ca13fb16f07238a2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789132"
---
# <a name="_efn_getmanagedobjectname-function"></a><span data-ttu-id="680bc-102">\_EFN\_GetManagedObjectName 関数</span><span class="sxs-lookup"><span data-stu-id="680bc-102">\_EFN\_GetManagedObjectName Function</span></span>
<span data-ttu-id="680bc-103">指定されたマネージオブジェクトポインターを使用して、型の名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="680bc-103">Gets the name of a type using the provided managed object pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="680bc-104">構文</span><span class="sxs-lookup"><span data-stu-id="680bc-104">Syntax</span></span>  
  
```cpp  
HRESULT _EFN_GetManagedObjectName(  
    [in]  PDEBUG_CLIENT  Client,  
    [in]  ULONG64        objAddr,  
    [out] __out_ecount(cbName) PSTR szName,  
    [out] ULONG          cbName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="680bc-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="680bc-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="680bc-106">からデバッグクライアントへのポインター。</span><span class="sxs-lookup"><span data-stu-id="680bc-106">[in] A pointer to the debug client.</span></span>  
  
 `objAddr`  
 <span data-ttu-id="680bc-107">からマネージオブジェクトポインター。</span><span class="sxs-lookup"><span data-stu-id="680bc-107">[in] A managed object pointer.</span></span>  
  
 <span data-ttu-id="680bc-108">szName</span><span class="sxs-lookup"><span data-stu-id="680bc-108">szName</span></span>  
 <span data-ttu-id="680bc-109">入出力型の名前。</span><span class="sxs-lookup"><span data-stu-id="680bc-109">[out] The name of the type.</span></span>  
  
 `cbName`  
 <span data-ttu-id="680bc-110">入出力文字列バッファーで使用できる文字数。</span><span class="sxs-lookup"><span data-stu-id="680bc-110">[out] The number of characters available in the string buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="680bc-111">コメント</span><span class="sxs-lookup"><span data-stu-id="680bc-111">Remarks</span></span>  
 <span data-ttu-id="680bc-112">現在コンテキスト内にあるスレッドにマネージコードがない場合、関数は、ファシリティ値が0xa0 でエラーコードが0x1000 の HRESULT SOS_E_NOMANAGEDCODE を返します。</span><span class="sxs-lookup"><span data-stu-id="680bc-112">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="680bc-113">要件</span><span class="sxs-lookup"><span data-stu-id="680bc-113">Requirements</span></span>  
 <span data-ttu-id="680bc-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="680bc-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="680bc-115">**ヘッダー:** SOS_Stacktrace</span><span class="sxs-lookup"><span data-stu-id="680bc-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="680bc-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="680bc-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="680bc-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="680bc-117">See also</span></span>

- [<span data-ttu-id="680bc-118">デバッグ グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="680bc-118">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)
