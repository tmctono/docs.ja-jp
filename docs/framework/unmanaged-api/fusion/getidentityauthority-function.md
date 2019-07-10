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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c5e8dd4a9dbf301b0910eda220513e9a3ffdc1cb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778641"
---
# <a name="getidentityauthority-function"></a><span data-ttu-id="52e3b-102">GetIdentityAuthority 関数</span><span class="sxs-lookup"><span data-stu-id="52e3b-102">GetIdentityAuthority Function</span></span>
<span data-ttu-id="52e3b-103">ポインターを取得、 [IIdentityAuthority](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md)コード オブジェクトのキーを管理するインスタンス。</span><span class="sxs-lookup"><span data-stu-id="52e3b-103">Gets a pointer to an [IIdentityAuthority](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md) instance that manages keys for code objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52e3b-104">構文</span><span class="sxs-lookup"><span data-stu-id="52e3b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIdentityAuthority (  
    [out] IIdentityAuthority   **ppIIdentityAuthority  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="52e3b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="52e3b-105">Parameters</span></span>  
 `ppIIdentityAuthority`  
 <span data-ttu-id="52e3b-106">[out]返された`IIdentityAuthority`ポインター。</span><span class="sxs-lookup"><span data-stu-id="52e3b-106">[out] The returned `IIdentityAuthority` pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52e3b-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="52e3b-107">Requirements</span></span>  
 <span data-ttu-id="52e3b-108">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="52e3b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52e3b-109">**ヘッダー:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="52e3b-109">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="52e3b-110">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52e3b-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52e3b-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="52e3b-111">See also</span></span>

- [<span data-ttu-id="52e3b-112">IIdentityAuthority インターフェイス</span><span class="sxs-lookup"><span data-stu-id="52e3b-112">IIdentityAuthority Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md)
- [<span data-ttu-id="52e3b-113">Fusion グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="52e3b-113">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
