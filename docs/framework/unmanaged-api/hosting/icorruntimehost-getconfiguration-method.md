---
title: ICorRuntimeHost::GetConfiguration メソッド
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.GetConfiguration
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::GetConfiguration
helpviewer_keywords:
- ICorRuntimeHost::GetConfiguration method [.NET Framework hosting]
- GetConfiguration method [.NET Framework hosting]
ms.assetid: c431617a-b055-44a0-8730-48b7a86d9610
topic_type:
- apiref
ms.openlocfilehash: 87549118742da797ef0dd1b08ae9e72c466f7841
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139567"
---
# <a name="icorruntimehostgetconfiguration-method"></a><span data-ttu-id="29688-102">ICorRuntimeHost::GetConfiguration メソッド</span><span class="sxs-lookup"><span data-stu-id="29688-102">ICorRuntimeHost::GetConfiguration Method</span></span>
<span data-ttu-id="29688-103">ホストが共通言語ランタイム (CLR) のコールバック構成を指定できるようにするオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="29688-103">Gets an object that allows the host to specify the callback configuration of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29688-104">構文</span><span class="sxs-lookup"><span data-stu-id="29688-104">Syntax</span></span>  
  
```cpp  
HRESULT GetConfiguration(  
    [out] ICorConfiguration** pConfiguration  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="29688-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="29688-105">Parameters</span></span>  
 `pConfiguration`  
 <span data-ttu-id="29688-106">入出力CLR の構成に使用できる[ICorConfiguration](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="29688-106">[out] A pointer to the address of an [ICorConfiguration](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md) object that can be used to configure the CLR.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="29688-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="29688-107">Remarks</span></span>  
 <span data-ttu-id="29688-108">CLR は、初期化の前に構成する必要があります。それ以外の場合、`GetConfiguration` メソッドはエラーを示す HRESULT を返します。</span><span class="sxs-lookup"><span data-stu-id="29688-108">The CLR must be configured prior to its initialization; otherwise, the `GetConfiguration` method returns an HRESULT indicating an error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29688-109">［要件］</span><span class="sxs-lookup"><span data-stu-id="29688-109">Requirements</span></span>  
 <span data-ttu-id="29688-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29688-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29688-111">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="29688-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="29688-112">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="29688-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="29688-113">**.NET Framework のバージョン:** 1.0、1.1</span><span class="sxs-lookup"><span data-stu-id="29688-113">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29688-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="29688-114">See also</span></span>

- [<span data-ttu-id="29688-115">ICorRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="29688-115">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
