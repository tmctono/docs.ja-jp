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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2f17a88a90905006432ae8c5dc040277124c947b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697291"
---
# <a name="comcallunmarshal-coclass"></a><span data-ttu-id="c46cc-102">ComCallUnmarshal コクラス</span><span class="sxs-lookup"><span data-stu-id="c46cc-102">ComCallUnmarshal Coclass</span></span>
<span data-ttu-id="c46cc-103">インターフェイス ポインターのマーシャ リングを管理するためのインターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="c46cc-103">Provides interfaces for managing the marshaling of interface pointers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c46cc-104">構文</span><span class="sxs-lookup"><span data-stu-id="c46cc-104">Syntax</span></span>  
  
```  
coclass ComCallUnmarshal {  
    [default] interface IMarshal;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="c46cc-105">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c46cc-105">Interfaces</span></span>  
  
|<span data-ttu-id="c46cc-106">Interface</span><span class="sxs-lookup"><span data-stu-id="c46cc-106">Interface</span></span>|<span data-ttu-id="c46cc-107">説明</span><span class="sxs-lookup"><span data-stu-id="c46cc-107">Description</span></span>|  
|---------------|-----------------|  
|`IMarshal`|<span data-ttu-id="c46cc-108">メソッドは、作成、初期化、およびクライアント プロセスでのプロキシの管理を提供します。</span><span class="sxs-lookup"><span data-stu-id="c46cc-108">Provides methods for creating, initializing, and managing a proxy in a client process.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c46cc-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="c46cc-109">Requirements</span></span>  
 <span data-ttu-id="c46cc-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c46cc-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c46cc-111">**ヘッダー:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="c46cc-111">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="c46cc-112">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="c46cc-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c46cc-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c46cc-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c46cc-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="c46cc-114">See also</span></span>

- [<span data-ttu-id="c46cc-115">ホスト コクラス</span><span class="sxs-lookup"><span data-stu-id="c46cc-115">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
