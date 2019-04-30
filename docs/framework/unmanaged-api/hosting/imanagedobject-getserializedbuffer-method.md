---
title: IManagedObject::GetSerializedBuffer メソッド
ms.date: 03/30/2017
api_name:
- IManagedObject.GetSerializedBuffer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetSerializedBuffer
helpviewer_keywords:
- IManagedObject::GetSerializedBuffer method [.NET Framework hosting]
- GetSerializedBuffer method [.NET Framework hosting]
ms.assetid: c17105bb-b49f-434e-8f9b-77f8c85b9220
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb9242160b684b3c7b90756d7b20811ad162fc30
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62043635"
---
# <a name="imanagedobjectgetserializedbuffer-method"></a><span data-ttu-id="bcfe1-102">IManagedObject::GetSerializedBuffer メソッド</span><span class="sxs-lookup"><span data-stu-id="bcfe1-102">IManagedObject::GetSerializedBuffer Method</span></span>
<span data-ttu-id="bcfe1-103">この管理対象のオブジェクトの文字列表現を取得します。</span><span class="sxs-lookup"><span data-stu-id="bcfe1-103">Gets the string representation of this managed object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcfe1-104">構文</span><span class="sxs-lookup"><span data-stu-id="bcfe1-104">Syntax</span></span>  
  
```  
HRESULT GetSerializedBuffer (  
    [out] BSTR *pBSTR  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bcfe1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bcfe1-105">Parameters</span></span>  
 `pBSTR`  
 <span data-ttu-id="bcfe1-106">[out]シリアル化されたオブジェクトを表す文字列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="bcfe1-106">[out] A pointer to a string that is the serialized object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bcfe1-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="bcfe1-107">Remarks</span></span>  
 <span data-ttu-id="bcfe1-108">`GetSerializedBuffer`メソッドは、クライアントにマーシャ リングできるように、オブジェクトをシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="bcfe1-108">The `GetSerializedBuffer` method serializes the object so it can be marshaled to the client.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bcfe1-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="bcfe1-109">Requirements</span></span>  
 <span data-ttu-id="bcfe1-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bcfe1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bcfe1-111">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="bcfe1-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bcfe1-112">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="bcfe1-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bcfe1-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bcfe1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcfe1-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="bcfe1-114">See also</span></span>

- [<span data-ttu-id="bcfe1-115">IManagedObject インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bcfe1-115">IManagedObject Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)
