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
ms.openlocfilehash: 8471610008bee02c7cc4e7654b21d6aca5dcf53a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796275"
---
# <a name="getappidauthority-function"></a><span data-ttu-id="58c15-102">GetAppIdAuthority 関数</span><span class="sxs-lookup"><span data-stu-id="58c15-102">GetAppIdAuthority Function</span></span>
<span data-ttu-id="58c15-103">アプリケーション id と参照のキーを管理する[Iappidauthority](iappidauthority-interface.md)インスタンスへのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="58c15-103">Gets a pointer to an [IAppIdAuthority](iappidauthority-interface.md) instance that manages keys for application identities and references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58c15-104">構文</span><span class="sxs-lookup"><span data-stu-id="58c15-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAppIdAuthority (  
    [out] IAppIdAuthority **ppIAppIdAuthority  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="58c15-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="58c15-105">Parameters</span></span>  
 `ppIAppIdAuthority`  
 <span data-ttu-id="58c15-106">入出力返され`IAppIdAuthority`たポインター。</span><span class="sxs-lookup"><span data-stu-id="58c15-106">[out] The returned `IAppIdAuthority` pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58c15-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="58c15-107">Requirements</span></span>  
 <span data-ttu-id="58c15-108">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="58c15-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58c15-109">**ヘッダー:** 分離 .h</span><span class="sxs-lookup"><span data-stu-id="58c15-109">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="58c15-110">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58c15-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58c15-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="58c15-111">See also</span></span>

- [<span data-ttu-id="58c15-112">IAppIdAuthority インターフェイス</span><span class="sxs-lookup"><span data-stu-id="58c15-112">IAppIdAuthority Interface</span></span>](iappidauthority-interface.md)
- [<span data-ttu-id="58c15-113">Fusion グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="58c15-113">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
