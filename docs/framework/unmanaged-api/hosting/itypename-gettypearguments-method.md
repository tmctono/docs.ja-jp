---
title: ITypeName::GetTypeArguments メソッド
ms.date: 03/30/2017
api_name:
- ITypeName.GetTypeArguments
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetTypeArguments
helpviewer_keywords:
- ITypeName::GetTypeArguments method [.NET Framework hosting]
- GetTypeArguments method [.NET Framework hosting]
ms.assetid: 638d77df-ff9c-40d9-88ee-930f5f87ada1
topic_type:
- apiref
ms.openlocfilehash: ac835459f88655377d96699e6aea0e877218c8fb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125281"
---
# <a name="itypenamegettypearguments-method"></a><span data-ttu-id="94691-102">ITypeName::GetTypeArguments メソッド</span><span class="sxs-lookup"><span data-stu-id="94691-102">ITypeName::GetTypeArguments Method</span></span>
<span data-ttu-id="94691-103">このメソッドは、.NET Framework インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="94691-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94691-104">構文</span><span class="sxs-lookup"><span data-stu-id="94691-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeArguments (  
    [in] DWORD           count,  
    [out] ITypeName**    rgpArguments,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="94691-105">［要件］</span><span class="sxs-lookup"><span data-stu-id="94691-105">Requirements</span></span>  
 <span data-ttu-id="94691-106">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94691-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94691-107">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="94691-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="94691-108">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="94691-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="94691-109">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94691-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94691-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="94691-110">See also</span></span>

- [<span data-ttu-id="94691-111">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="94691-111">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
