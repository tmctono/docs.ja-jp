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
ms.openlocfilehash: cbd6fa5f7935a57799d695c3ebb617d856e6dbd9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133177"
---
# <a name="idebuggerinfoisdebuggerattached-method"></a><span data-ttu-id="b07ba-102">IDebuggerInfo::IsDebuggerAttached メソッド</span><span class="sxs-lookup"><span data-stu-id="b07ba-102">IDebuggerInfo::IsDebuggerAttached Method</span></span>
<span data-ttu-id="b07ba-103">マネージデバッガーがこのプロセスにアタッチされているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="b07ba-103">Gets a value that indicates whether a managed debugger is attached to this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b07ba-104">構文</span><span class="sxs-lookup"><span data-stu-id="b07ba-104">Syntax</span></span>  
  
```cpp  
HRESULT IsDebuggerAttached (  
    [out] BOOL *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b07ba-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b07ba-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="b07ba-106">入出力マネージデバッガーがプロセスにアタッチされている場合に `true` される値へのポインター。それ以外の場合は、`false`ます。</span><span class="sxs-lookup"><span data-stu-id="b07ba-106">[out] A pointer to a value that is `true` if a managed debugger is attached to the process; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b07ba-107">［要件］</span><span class="sxs-lookup"><span data-stu-id="b07ba-107">Requirements</span></span>  
 <span data-ttu-id="b07ba-108">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b07ba-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b07ba-109">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b07ba-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b07ba-110">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="b07ba-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b07ba-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b07ba-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b07ba-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="b07ba-112">See also</span></span>

- [<span data-ttu-id="b07ba-113">IDebuggerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b07ba-113">IDebuggerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)
