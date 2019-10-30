---
title: ITypeNameBuilder::ToString メソッド
ms.date: 03/30/2017
api_name:
- ITypeNameBuilder.ToString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ToString
helpviewer_keywords:
- ToString method [.NET Framework hosting]
- ITypeNameBuilder::ToString method [.NET Framework hosting]
ms.assetid: 6372aca7-869a-4af6-ba2b-0eb1047ef5c0
topic_type:
- apiref
ms.openlocfilehash: 531bd3ffe00c12ef580e8341cd6ad1f7d3924717
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123356"
---
# <a name="itypenamebuildertostring-method"></a><span data-ttu-id="bea79-102">ITypeNameBuilder::ToString メソッド</span><span class="sxs-lookup"><span data-stu-id="bea79-102">ITypeNameBuilder::ToString Method</span></span>
<span data-ttu-id="bea79-103">このメソッドは、.NET Framework インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="bea79-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bea79-104">構文</span><span class="sxs-lookup"><span data-stu-id="bea79-104">Syntax</span></span>  
  
```cpp  
HRESULT ToString (  
    [out, retval] BSTR* pszStringRepresentation  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="bea79-105">［要件］</span><span class="sxs-lookup"><span data-stu-id="bea79-105">Requirements</span></span>  
 <span data-ttu-id="bea79-106">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bea79-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bea79-107">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="bea79-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bea79-108">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="bea79-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bea79-109">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bea79-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bea79-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="bea79-110">See also</span></span>

- [<span data-ttu-id="bea79-111">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bea79-111">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
