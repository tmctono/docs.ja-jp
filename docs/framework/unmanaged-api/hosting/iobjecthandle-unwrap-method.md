---
title: IObjectHandle::Unwrap メソッド
ms.date: 03/30/2017
api_name:
- IObjectHandle.Unwrap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- Unwrap
helpviewer_keywords:
- Unwrap method [.NET Framework hosting]
- IObjectHandle::Unwrap method [.NET Framework hosting]
ms.assetid: 794c6f8e-ed58-416b-b756-e864f2c958f7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4c18607d5373b415228846350a3dd0637ade1b45
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61917593"
---
# <a name="iobjecthandleunwrap-method"></a><span data-ttu-id="af873-102">IObjectHandle::Unwrap メソッド</span><span class="sxs-lookup"><span data-stu-id="af873-102">IObjectHandle::Unwrap Method</span></span>
<span data-ttu-id="af873-103">間接参照から値渡しのマーシャ リングするオブジェクトをアンラップされます。</span><span class="sxs-lookup"><span data-stu-id="af873-103">Unwraps a marshal-by-value object from indirection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af873-104">構文</span><span class="sxs-lookup"><span data-stu-id="af873-104">Syntax</span></span>  
  
```  
HRESULT Unwrap (  
    [out, retval] VARIANT *ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="af873-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="af873-105">Parameters</span></span>  
 `ppv`  
 <span data-ttu-id="af873-106">[out]ラップするオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="af873-106">[out] A pointer to the object to be unwrapped.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af873-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="af873-107">Requirements</span></span>  
 <span data-ttu-id="af873-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="af873-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af873-109">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="af873-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="af873-110">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="af873-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="af873-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af873-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
