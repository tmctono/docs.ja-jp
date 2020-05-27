---
title: IDebuggerInfo::IsDebuggerAttached メソッド
ms.date: 03/30/2017
api_name:
- IDebuggerInfo.IsDebuggerAttached
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IsDebuggerAttached
helpviewer_keywords:
- IDebuggerInfo::IsDebuggerAttached method [.NET Framework hosting]
- IsDebuggerAttached method, IDebuggerInfo interface [.NET Framework hosting]
ms.assetid: 6e21872f-602f-411a-a423-bff5cdf27000
topic_type:
- apiref
ms.openlocfilehash: 95b7a2f6d35104c3353853549dacc783355feb5b
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805334"
---
# <a name="idebuggerinfoisdebuggerattached-method"></a><span data-ttu-id="ec5db-102">IDebuggerInfo::IsDebuggerAttached メソッド</span><span class="sxs-lookup"><span data-stu-id="ec5db-102">IDebuggerInfo::IsDebuggerAttached Method</span></span>
<span data-ttu-id="ec5db-103">マネージデバッガーがこのプロセスにアタッチされているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="ec5db-103">Gets a value that indicates whether a managed debugger is attached to this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec5db-104">構文</span><span class="sxs-lookup"><span data-stu-id="ec5db-104">Syntax</span></span>  
  
```cpp  
HRESULT IsDebuggerAttached (  
    [out] BOOL *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec5db-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ec5db-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="ec5db-106">入出力`true`マネージデバッガーがプロセスにアタッチされている場合は値を指すポインター。それ以外の場合は `false` 。</span><span class="sxs-lookup"><span data-stu-id="ec5db-106">[out] A pointer to a value that is `true` if a managed debugger is attached to the process; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec5db-107">要件</span><span class="sxs-lookup"><span data-stu-id="ec5db-107">Requirements</span></span>  
 <span data-ttu-id="ec5db-108">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec5db-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec5db-109">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="ec5db-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ec5db-110">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="ec5db-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ec5db-111">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec5db-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec5db-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="ec5db-112">See also</span></span>

- [<span data-ttu-id="ec5db-113">IDebuggerInfo Iインターフェイス</span><span class="sxs-lookup"><span data-stu-id="ec5db-113">IDebuggerInfo Interface</span></span>](idebuggerinfo-interface.md)
