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
ms.openlocfilehash: 939acc0ad47021d5fdffe7b7b71ea6a4a1635a6d
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616737"
---
# <a name="comcallunmarshal-coclass"></a><span data-ttu-id="b20d0-102">ComCallUnmarshal コクラス</span><span class="sxs-lookup"><span data-stu-id="b20d0-102">ComCallUnmarshal Coclass</span></span>
<span data-ttu-id="b20d0-103">インターフェイスポインターのマーシャリングを管理するためのインターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="b20d0-103">Provides interfaces for managing the marshaling of interface pointers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b20d0-104">構文</span><span class="sxs-lookup"><span data-stu-id="b20d0-104">Syntax</span></span>  
  
```cpp  
coclass ComCallUnmarshal {  
    [default] interface IMarshal;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="b20d0-105">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b20d0-105">Interfaces</span></span>  
  
|<span data-ttu-id="b20d0-106">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b20d0-106">Interface</span></span>|<span data-ttu-id="b20d0-107">説明</span><span class="sxs-lookup"><span data-stu-id="b20d0-107">Description</span></span>|  
|---------------|-----------------|  
|`IMarshal`|<span data-ttu-id="b20d0-108">クライアントプロセスでプロキシを作成、初期化、および管理するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="b20d0-108">Provides methods for creating, initializing, and managing a proxy in a client process.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b20d0-109">要件</span><span class="sxs-lookup"><span data-stu-id="b20d0-109">Requirements</span></span>  
 <span data-ttu-id="b20d0-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b20d0-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b20d0-111">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b20d0-111">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="b20d0-112">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="b20d0-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b20d0-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b20d0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b20d0-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="b20d0-114">See also</span></span>

- [<span data-ttu-id="b20d0-115">ホスト コクラス</span><span class="sxs-lookup"><span data-stu-id="b20d0-115">Hosting Coclasses</span></span>](hosting-coclasses.md)
