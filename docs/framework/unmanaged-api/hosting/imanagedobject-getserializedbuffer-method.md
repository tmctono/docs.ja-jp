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
ms.openlocfilehash: 4a55ae265230c4da3cc0a19b06a7597be8661beb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73103247"
---
# <a name="imanagedobjectgetserializedbuffer-method"></a><span data-ttu-id="761ba-102">IManagedObject::GetSerializedBuffer メソッド</span><span class="sxs-lookup"><span data-stu-id="761ba-102">IManagedObject::GetSerializedBuffer Method</span></span>
<span data-ttu-id="761ba-103">このマネージオブジェクトの文字列表現を取得します。</span><span class="sxs-lookup"><span data-stu-id="761ba-103">Gets the string representation of this managed object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="761ba-104">構文</span><span class="sxs-lookup"><span data-stu-id="761ba-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSerializedBuffer (  
    [out] BSTR *pBSTR  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="761ba-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="761ba-105">Parameters</span></span>  
 `pBSTR`  
 <span data-ttu-id="761ba-106">入出力シリアル化されたオブジェクトである文字列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="761ba-106">[out] A pointer to a string that is the serialized object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="761ba-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="761ba-107">Remarks</span></span>  
 <span data-ttu-id="761ba-108">`GetSerializedBuffer` メソッドは、オブジェクトをシリアル化してクライアントにマーシャリングできるようにします。</span><span class="sxs-lookup"><span data-stu-id="761ba-108">The `GetSerializedBuffer` method serializes the object so it can be marshaled to the client.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="761ba-109">［要件］</span><span class="sxs-lookup"><span data-stu-id="761ba-109">Requirements</span></span>  
 <span data-ttu-id="761ba-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="761ba-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="761ba-111">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="761ba-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="761ba-112">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="761ba-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="761ba-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="761ba-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="761ba-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="761ba-114">See also</span></span>

- [<span data-ttu-id="761ba-115">IManagedObject インターフェイス</span><span class="sxs-lookup"><span data-stu-id="761ba-115">IManagedObject Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)
