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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0708a3b501a99b5f71be5ba4c6cc4ea2b754d12a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61699891"
---
# <a name="idebuggerinfoisdebuggerattached-method"></a><span data-ttu-id="16d04-102">IDebuggerInfo::IsDebuggerAttached メソッド</span><span class="sxs-lookup"><span data-stu-id="16d04-102">IDebuggerInfo::IsDebuggerAttached Method</span></span>
<span data-ttu-id="16d04-103">マネージ デバッガーがこのプロセスにアタッチされているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="16d04-103">Gets a value that indicates whether a managed debugger is attached to this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16d04-104">構文</span><span class="sxs-lookup"><span data-stu-id="16d04-104">Syntax</span></span>  
  
```  
HRESULT IsDebuggerAttached (  
    [out] BOOL *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="16d04-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="16d04-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="16d04-106">[out]ある値へのポインター`true`マネージ デバッガーがプロセスにアタッチされている。 それ以外の場合`false`します。</span><span class="sxs-lookup"><span data-stu-id="16d04-106">[out] A pointer to a value that is `true` if a managed debugger is attached to the process; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16d04-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="16d04-107">Requirements</span></span>  
 <span data-ttu-id="16d04-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="16d04-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16d04-109">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="16d04-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="16d04-110">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="16d04-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="16d04-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16d04-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16d04-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="16d04-112">See also</span></span>

- [<span data-ttu-id="16d04-113">IDebuggerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="16d04-113">IDebuggerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)
