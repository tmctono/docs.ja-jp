---
title: GetIdentityAuthority 関数
ms.date: 03/30/2017
api_name:
- GetIdentityAuthority
api_location:
- fusion.dll
- clr.dll
api_type:
- COM
f1_keywords:
- GetIdentityAuthority
helpviewer_keywords:
- GetIdentityAuthority function [.NET Framework fusion]
ms.assetid: 843cd5ab-d2b7-4ff6-86bd-e68c7a91c098
topic_type:
- apiref
ms.openlocfilehash: acb80f3cc199d4d9f774cb3898335d26fe44b807
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127141"
---
# <a name="getidentityauthority-function"></a><span data-ttu-id="f57c5-102">GetIdentityAuthority 関数</span><span class="sxs-lookup"><span data-stu-id="f57c5-102">GetIdentityAuthority Function</span></span>
<span data-ttu-id="f57c5-103">コードオブジェクトのキーを管理する[Iidentity authority](iidentityauthority-interface.md)インスタンスへのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="f57c5-103">Gets a pointer to an [IIdentityAuthority](iidentityauthority-interface.md) instance that manages keys for code objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f57c5-104">構文</span><span class="sxs-lookup"><span data-stu-id="f57c5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIdentityAuthority (  
    [out] IIdentityAuthority   **ppIIdentityAuthority  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="f57c5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f57c5-105">Parameters</span></span>  
 `ppIIdentityAuthority`  
 <span data-ttu-id="f57c5-106">入出力返された `IIdentityAuthority` ポインター。</span><span class="sxs-lookup"><span data-stu-id="f57c5-106">[out] The returned `IIdentityAuthority` pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f57c5-107">［要件］</span><span class="sxs-lookup"><span data-stu-id="f57c5-107">Requirements</span></span>  
 <span data-ttu-id="f57c5-108">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f57c5-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f57c5-109">**ヘッダー:** 分離 .h</span><span class="sxs-lookup"><span data-stu-id="f57c5-109">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="f57c5-110">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f57c5-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f57c5-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="f57c5-111">See also</span></span>

- [<span data-ttu-id="f57c5-112">IIdentityAuthority インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f57c5-112">IIdentityAuthority Interface</span></span>](iidentityauthority-interface.md)
- [<span data-ttu-id="f57c5-113">Fusion グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="f57c5-113">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
