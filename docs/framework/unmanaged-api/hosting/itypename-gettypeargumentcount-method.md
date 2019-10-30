---
title: ITypeName::GetTypeArgumentCount メソッド
ms.date: 03/30/2017
api_name:
- ITypeName.GetTypeArgumentCount
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetTypeArgumentCount
helpviewer_keywords:
- GetTypeArgumentCount method [.NET Framework hosting]
- ITypeName::GetTypeArgumentCount method [.NET Framework hosting]
ms.assetid: ecb5480c-761a-4b02-83e0-b79abc67fd08
topic_type:
- apiref
ms.openlocfilehash: 2b332c39ea38734babca4c72b9e74b1c6b29bc73
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73095463"
---
# <a name="itypenamegettypeargumentcount-method"></a><span data-ttu-id="70fa1-102">ITypeName::GetTypeArgumentCount メソッド</span><span class="sxs-lookup"><span data-stu-id="70fa1-102">ITypeName::GetTypeArgumentCount Method</span></span>
<span data-ttu-id="70fa1-103">このメソッドは、.NET Framework インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="70fa1-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70fa1-104">構文</span><span class="sxs-lookup"><span data-stu-id="70fa1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeArgumentCount (  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="70fa1-105">［要件］</span><span class="sxs-lookup"><span data-stu-id="70fa1-105">Requirements</span></span>  
 <span data-ttu-id="70fa1-106">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70fa1-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70fa1-107">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="70fa1-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="70fa1-108">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="70fa1-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="70fa1-109">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70fa1-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70fa1-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="70fa1-110">See also</span></span>

- [<span data-ttu-id="70fa1-111">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="70fa1-111">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
