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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59191342"
---
# <a name="idebuggerinfoisdebuggerattached-method"></a><span data-ttu-id="118ed-102">IDebuggerInfo::IsDebuggerAttached メソッド</span><span class="sxs-lookup"><span data-stu-id="118ed-102">IDebuggerInfo::IsDebuggerAttached Method</span></span>
<span data-ttu-id="118ed-103">マネージ デバッガーがこのプロセスにアタッチされているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="118ed-103">Gets a value that indicates whether a managed debugger is attached to this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="118ed-104">構文</span><span class="sxs-lookup"><span data-stu-id="118ed-104">Syntax</span></span>  
  
```  
HRESULT IsDebuggerAttached (  
    [out] BOOL *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="118ed-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="118ed-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="118ed-106">[out]ある値へのポインター`true`マネージ デバッガーがプロセスにアタッチされている。 それ以外の場合`false`します。</span><span class="sxs-lookup"><span data-stu-id="118ed-106">[out] A pointer to a value that is `true` if a managed debugger is attached to the process; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="118ed-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="118ed-107">Requirements</span></span>  
 <span data-ttu-id="118ed-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="118ed-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="118ed-109">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="118ed-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="118ed-110">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="118ed-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="118ed-111">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="118ed-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="118ed-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="118ed-112">See also</span></span>

- [<span data-ttu-id="118ed-113">IDebuggerInfo Iインターフェイス</span><span class="sxs-lookup"><span data-stu-id="118ed-113">IDebuggerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)
