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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cf74da6eb0e7ce0215023a9a58d6b88c57c4fe8b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59097337"
---
# <a name="icorruntimehostgetconfiguration-method"></a><span data-ttu-id="8e360-102">ICorRuntimeHost::GetConfiguration メソッド</span><span class="sxs-lookup"><span data-stu-id="8e360-102">ICorRuntimeHost::GetConfiguration Method</span></span>
<span data-ttu-id="8e360-103">共通言語ランタイム (CLR) のコールバックの構成を指定するホストをできるようにするオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="8e360-103">Gets an object that allows the host to specify the callback configuration of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e360-104">構文</span><span class="sxs-lookup"><span data-stu-id="8e360-104">Syntax</span></span>  
  
```  
HRESULT GetConfiguration(  
    [out] ICorConfiguration** pConfiguration  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8e360-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8e360-105">Parameters</span></span>  
 `pConfiguration`  
 <span data-ttu-id="8e360-106">[out]アドレスへのポインター、 [ICorConfiguration](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md) CLR を構成するために使用できるオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="8e360-106">[out] A pointer to the address of an [ICorConfiguration](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md) object that can be used to configure the CLR.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8e360-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="8e360-107">Remarks</span></span>  
 <span data-ttu-id="8e360-108">CLR は、初期化する前に構成する必要があります。それ以外の場合、`GetConfiguration`メソッドはエラーを示す HRESULT を返します。</span><span class="sxs-lookup"><span data-stu-id="8e360-108">The CLR must be configured prior to its initialization; otherwise, the `GetConfiguration` method returns an HRESULT indicating an error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e360-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="8e360-109">Requirements</span></span>  
 <span data-ttu-id="8e360-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e360-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e360-111">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8e360-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8e360-112">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="8e360-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8e360-113">**.NET framework のバージョン:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="8e360-113">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e360-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="8e360-114">See also</span></span>

- [<span data-ttu-id="8e360-115">ICorRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8e360-115">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
