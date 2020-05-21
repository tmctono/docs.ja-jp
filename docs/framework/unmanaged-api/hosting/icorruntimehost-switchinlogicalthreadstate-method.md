---
title: ICorRuntimeHost::SwitchInLogicalThreadState メソッド
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.SwitchInLogicalThreadState
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::SwitchInLogicalThreadState
helpviewer_keywords:
- ICorRuntimeHost::SwitchInLogicalThreadState method [.NET Framework hosting]
- SwitchInLogicalThreadState method [.NET Framework hosting]
ms.assetid: 7df1e492-8014-43ea-80d1-a4743e9b1c17
topic_type:
- apiref
ms.openlocfilehash: d830635b911fa5d80382e432f283c455c41af7a8
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762683"
---
# <a name="icorruntimehostswitchinlogicalthreadstate-method"></a><span data-ttu-id="16124-102">ICorRuntimeHost::SwitchInLogicalThreadState メソッド</span><span class="sxs-lookup"><span data-stu-id="16124-102">ICorRuntimeHost::SwitchInLogicalThreadState Method</span></span>
<span data-ttu-id="16124-103">このメソッドは、.NET Framework インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="16124-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16124-104">構文</span><span class="sxs-lookup"><span data-stu-id="16124-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchInLogicalThreadState(  
    [in] DWORD *pFiberCookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="16124-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="16124-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="16124-106">から使用するファイバーを示すクッキー。</span><span class="sxs-lookup"><span data-stu-id="16124-106">[in] Cookie that indicates the fiber to use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16124-107">要件</span><span class="sxs-lookup"><span data-stu-id="16124-107">Requirements</span></span>  
 <span data-ttu-id="16124-108">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16124-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16124-109">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="16124-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="16124-110">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="16124-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="16124-111">**.NET Framework バージョン:** 1.0、1.1</span><span class="sxs-lookup"><span data-stu-id="16124-111">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16124-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="16124-112">See also</span></span>

- [<span data-ttu-id="16124-113">ICorRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="16124-113">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
