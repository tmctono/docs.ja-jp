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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 88c2818bd3ad86e7683ffbe6c5454fca560dacde
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67757742"
---
# <a name="itypenamegettypeargumentcount-method"></a><span data-ttu-id="5068f-102">ITypeName::GetTypeArgumentCount メソッド</span><span class="sxs-lookup"><span data-stu-id="5068f-102">ITypeName::GetTypeArgumentCount Method</span></span>
<span data-ttu-id="5068f-103">このメソッドは、.NET Framework インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="5068f-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5068f-104">構文</span><span class="sxs-lookup"><span data-stu-id="5068f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeArgumentCount (  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="5068f-105">必要条件</span><span class="sxs-lookup"><span data-stu-id="5068f-105">Requirements</span></span>  
 <span data-ttu-id="5068f-106">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5068f-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5068f-107">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5068f-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5068f-108">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="5068f-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5068f-109">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5068f-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5068f-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="5068f-110">See also</span></span>

- [<span data-ttu-id="5068f-111">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5068f-111">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
