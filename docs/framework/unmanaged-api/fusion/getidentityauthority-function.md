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
ms.openlocfilehash: f29246bdb929c8eaf1ebce726164d5cd2269b9f1
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796859"
---
# <a name="getidentityauthority-function"></a><span data-ttu-id="66432-102">GetIdentityAuthority 関数</span><span class="sxs-lookup"><span data-stu-id="66432-102">GetIdentityAuthority Function</span></span>
<span data-ttu-id="66432-103">コードオブジェクトのキーを管理する[Iidentity authority](iidentityauthority-interface.md)インスタンスへのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="66432-103">Gets a pointer to an [IIdentityAuthority](iidentityauthority-interface.md) instance that manages keys for code objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66432-104">構文</span><span class="sxs-lookup"><span data-stu-id="66432-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIdentityAuthority (  
    [out] IIdentityAuthority   **ppIIdentityAuthority  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="66432-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="66432-105">Parameters</span></span>  
 `ppIIdentityAuthority`  
 <span data-ttu-id="66432-106">入出力返され`IIdentityAuthority`たポインター。</span><span class="sxs-lookup"><span data-stu-id="66432-106">[out] The returned `IIdentityAuthority` pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66432-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="66432-107">Requirements</span></span>  
 <span data-ttu-id="66432-108">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="66432-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66432-109">**ヘッダー:** 分離 .h</span><span class="sxs-lookup"><span data-stu-id="66432-109">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="66432-110">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66432-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66432-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="66432-111">See also</span></span>

- [<span data-ttu-id="66432-112">IIdentityAuthority インターフェイス</span><span class="sxs-lookup"><span data-stu-id="66432-112">IIdentityAuthority Interface</span></span>](iidentityauthority-interface.md)
- [<span data-ttu-id="66432-113">Fusion グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="66432-113">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
