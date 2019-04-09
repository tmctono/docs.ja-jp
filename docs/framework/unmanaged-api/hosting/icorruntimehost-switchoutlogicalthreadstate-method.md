---
title: ICorRuntimeHost::SwitchOutLogicalThreadState メソッド
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.SwitchOutLogicalThreadState
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::SwitchOutLogicalThreadState
helpviewer_keywords:
- ICorRuntimeHost::SwitchOutLogicalThreadState method [.NET Framework hosting]
- SwitchOutLogicalThreadState method [.NET Framework hosting]
ms.assetid: e1968f0b-2675-4dc2-8507-46164e1df154
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1291d4e69843db7bd90af07291da415220d98807
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59131359"
---
# <a name="icorruntimehostswitchoutlogicalthreadstate-method"></a><span data-ttu-id="19cf8-102">ICorRuntimeHost::SwitchOutLogicalThreadState メソッド</span><span class="sxs-lookup"><span data-stu-id="19cf8-102">ICorRuntimeHost::SwitchOutLogicalThreadState Method</span></span>
<span data-ttu-id="19cf8-103">このメソッドは、.NET Framework インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="19cf8-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19cf8-104">構文</span><span class="sxs-lookup"><span data-stu-id="19cf8-104">Syntax</span></span>  
  
```  
HRESULT SwitchOutLogicalThreadState(  
    [out] DWORD **pFiberCookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="19cf8-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="19cf8-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="19cf8-106">[out]切り替え元とされているファイバーを示すクッキー。</span><span class="sxs-lookup"><span data-stu-id="19cf8-106">[out] Cookie that indicates the fiber being switched out.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19cf8-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="19cf8-107">Requirements</span></span>  
 <span data-ttu-id="19cf8-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="19cf8-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19cf8-109">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="19cf8-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="19cf8-110">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="19cf8-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="19cf8-111">**.NET framework のバージョン:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="19cf8-111">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19cf8-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="19cf8-112">See also</span></span>

- [<span data-ttu-id="19cf8-113">ICorRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="19cf8-113">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
