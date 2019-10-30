---
title: ComCallUnmarshal コクラス
ms.date: 03/30/2017
api_name:
- ComCallUnmarshal Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ComCallUnmarshal
helpviewer_keywords:
- ComCallUnmarshal coclass [.NET Framework hosting]
ms.assetid: 2adb5827-2268-4914-a1c6-f62b61880a45
topic_type:
- apiref
ms.openlocfilehash: 38f3140a181deae1a86569bfc2eb7cf3cd7d1991
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131926"
---
# <a name="comcallunmarshal-coclass"></a><span data-ttu-id="b5e0f-102">ComCallUnmarshal コクラス</span><span class="sxs-lookup"><span data-stu-id="b5e0f-102">ComCallUnmarshal Coclass</span></span>
<span data-ttu-id="b5e0f-103">インターフェイスポインターのマーシャリングを管理するためのインターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="b5e0f-103">Provides interfaces for managing the marshaling of interface pointers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5e0f-104">構文</span><span class="sxs-lookup"><span data-stu-id="b5e0f-104">Syntax</span></span>  
  
```cpp  
coclass ComCallUnmarshal {  
    [default] interface IMarshal;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="b5e0f-105">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b5e0f-105">Interfaces</span></span>  
  
|<span data-ttu-id="b5e0f-106">Interface</span><span class="sxs-lookup"><span data-stu-id="b5e0f-106">Interface</span></span>|<span data-ttu-id="b5e0f-107">説明</span><span class="sxs-lookup"><span data-stu-id="b5e0f-107">Description</span></span>|  
|---------------|-----------------|  
|`IMarshal`|<span data-ttu-id="b5e0f-108">クライアントプロセスでプロキシを作成、初期化、および管理するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="b5e0f-108">Provides methods for creating, initializing, and managing a proxy in a client process.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b5e0f-109">［要件］</span><span class="sxs-lookup"><span data-stu-id="b5e0f-109">Requirements</span></span>  
 <span data-ttu-id="b5e0f-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5e0f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5e0f-111">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b5e0f-111">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="b5e0f-112">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="b5e0f-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b5e0f-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5e0f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5e0f-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="b5e0f-114">See also</span></span>

- [<span data-ttu-id="b5e0f-115">ホスト コクラス</span><span class="sxs-lookup"><span data-stu-id="b5e0f-115">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
