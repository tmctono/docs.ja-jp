---
title: ITypeName::GetModifiers メソッド
ms.date: 03/30/2017
api_name:
- ITypeName.GetModifiers
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetModifiers
helpviewer_keywords:
- ITypeName::GetModifiers method [.NET Framework hosting]
- GetModifiers method [.NET Framework hosting]
ms.assetid: 75508c55-3e09-4135-80da-cc811003fa82
topic_type:
- apiref
ms.openlocfilehash: c96764749a766f3b4bbff4cf6512677a47197f4c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73095833"
---
# <a name="itypenamegetmodifiers-method"></a><span data-ttu-id="642ae-102">ITypeName::GetModifiers メソッド</span><span class="sxs-lookup"><span data-stu-id="642ae-102">ITypeName::GetModifiers Method</span></span>
<span data-ttu-id="642ae-103">このメソッドは、.NET Framework インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="642ae-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="642ae-104">構文</span><span class="sxs-lookup"><span data-stu-id="642ae-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModifiers (  
    [in] DWORD           count,  
    [out] DWORD*         rgModifiers,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="642ae-105">［要件］</span><span class="sxs-lookup"><span data-stu-id="642ae-105">Requirements</span></span>  
 <span data-ttu-id="642ae-106">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="642ae-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="642ae-107">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="642ae-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="642ae-108">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="642ae-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="642ae-109">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="642ae-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="642ae-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="642ae-110">See also</span></span>

- [<span data-ttu-id="642ae-111">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="642ae-111">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
