---
title: GetAppIdAuthority 関数
ms.date: 03/30/2017
api_name:
- GetAppIdAuthority
api_location:
- fusion.dll
- clr.dll
api_type:
- COM
f1_keywords:
- GetAppIdAuthority
helpviewer_keywords:
- GetAppIdAuthority function [.NET Framework fusion]
ms.assetid: 9f968dad-0d09-47fb-bebc-94c39a0d16ad
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 536f3249593333234f7f09921007b483fb80cf79
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778592"
---
# <a name="getappidauthority-function"></a><span data-ttu-id="9ee4d-102">GetAppIdAuthority 関数</span><span class="sxs-lookup"><span data-stu-id="9ee4d-102">GetAppIdAuthority Function</span></span>
<span data-ttu-id="9ee4d-103">ポインターを取得、 [IAppIdAuthority](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md)アプリケーション id と参照のキーを管理するインスタンス。</span><span class="sxs-lookup"><span data-stu-id="9ee4d-103">Gets a pointer to an [IAppIdAuthority](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md) instance that manages keys for application identities and references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ee4d-104">構文</span><span class="sxs-lookup"><span data-stu-id="9ee4d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAppIdAuthority (  
    [out] IAppIdAuthority **ppIAppIdAuthority  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="9ee4d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9ee4d-105">Parameters</span></span>  
 `ppIAppIdAuthority`  
 <span data-ttu-id="9ee4d-106">[out]返された`IAppIdAuthority`ポインター。</span><span class="sxs-lookup"><span data-stu-id="9ee4d-106">[out] The returned `IAppIdAuthority` pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ee4d-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="9ee4d-107">Requirements</span></span>  
 <span data-ttu-id="9ee4d-108">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ee4d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ee4d-109">**ヘッダー:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="9ee4d-109">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="9ee4d-110">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ee4d-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ee4d-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="9ee4d-111">See also</span></span>

- [<span data-ttu-id="9ee4d-112">IAppIdAuthority インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9ee4d-112">IAppIdAuthority Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md)
- [<span data-ttu-id="9ee4d-113">Fusion グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="9ee4d-113">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
