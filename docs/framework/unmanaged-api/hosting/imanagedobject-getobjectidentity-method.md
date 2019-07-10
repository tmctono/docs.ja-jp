---
title: IManagedObject::GetObjectIdentity メソッド
ms.date: 03/30/2017
api_name:
- IManagedObject.GetObjectIdentity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetObjectIdentity
helpviewer_keywords:
- GetObjectIdentity method [.NET Framework hosting]
- IManagedObject::GetObjectIdentity method [.NET Framework hosting]
ms.assetid: b862ff3e-e480-4cdf-84e2-e1013334a467
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 291246169a5cc2c95b117bc55bc269791885b2ea
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749106"
---
# <a name="imanagedobjectgetobjectidentity-method"></a><span data-ttu-id="48257-102">IManagedObject::GetObjectIdentity メソッド</span><span class="sxs-lookup"><span data-stu-id="48257-102">IManagedObject::GetObjectIdentity Method</span></span>
<span data-ttu-id="48257-103">この管理対象のオブジェクトの id を取得します。</span><span class="sxs-lookup"><span data-stu-id="48257-103">Gets the identity of this managed object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48257-104">構文</span><span class="sxs-lookup"><span data-stu-id="48257-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectIdentity (  
    [out] BSTR*   pBSTRGUID,  
    [out] int*    AppDomainID,  
    [out] CCW_PTR pCCW  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48257-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="48257-105">Parameters</span></span>  
 `pBSTRGUID`  
 <span data-ttu-id="48257-106">[out]オブジェクトが存在するプロセスの GUID へのポインター。</span><span class="sxs-lookup"><span data-stu-id="48257-106">[out] A pointer to the GUID of the process in which the object resides.</span></span>  
  
 `AppDomainID`  
 <span data-ttu-id="48257-107">[out]オブジェクトのアプリケーション ドメインの ID へのポインター。</span><span class="sxs-lookup"><span data-stu-id="48257-107">[out] A pointer to the ID of the object's application domain.</span></span>  
  
 `pCCW`  
 <span data-ttu-id="48257-108">[out]V-table という COM クラシックでのオブジェクトのインデックスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="48257-108">[out] A pointer to object's index in the COM classic v-table.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="48257-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="48257-109">Remarks</span></span>  
 <span data-ttu-id="48257-110">マネージ オブジェクトの id には、v-table という COM クラシックでのプロセス GUID、アプリケーション ドメイン ID、およびオブジェクトのインデックスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="48257-110">The identity of a managed object includes process GUID, application domain ID, and the object's index in the COM classic v-table.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48257-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="48257-111">Requirements</span></span>  
 <span data-ttu-id="48257-112">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="48257-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48257-113">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="48257-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="48257-114">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="48257-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="48257-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48257-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48257-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="48257-116">See also</span></span>

- [<span data-ttu-id="48257-117">IManagedObject インターフェイス</span><span class="sxs-lookup"><span data-stu-id="48257-117">IManagedObject Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)
