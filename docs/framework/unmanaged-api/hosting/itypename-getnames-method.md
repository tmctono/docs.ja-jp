---
title: ITypeName::GetNames メソッド
ms.date: 03/30/2017
api_name:
- ITypeName.GetNames
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetNames
helpviewer_keywords:
- ITypeName::GetNames method [.NET Framework hosting]
- GetNames method [.NET Framework hosting]
ms.assetid: e2a3637b-d1e9-4d93-9e9b-0555fbff793d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 28076a36880febad20d457ff5a6b290de3d6f173
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61672979"
---
# <a name="itypenamegetnames-method"></a><span data-ttu-id="e3c73-102">ITypeName::GetNames メソッド</span><span class="sxs-lookup"><span data-stu-id="e3c73-102">ITypeName::GetNames Method</span></span>
<span data-ttu-id="e3c73-103">このメソッドは、.NET Framework インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="e3c73-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3c73-104">構文</span><span class="sxs-lookup"><span data-stu-id="e3c73-104">Syntax</span></span>  
  
```  
HRESULT GetNames (  
    [in] DWORD           count,  
    [out] BSTR*          rgbszNames,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="e3c73-105">必要条件</span><span class="sxs-lookup"><span data-stu-id="e3c73-105">Requirements</span></span>  
 <span data-ttu-id="e3c73-106">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3c73-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3c73-107">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e3c73-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e3c73-108">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="e3c73-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e3c73-109">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3c73-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3c73-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="e3c73-110">See also</span></span>

- [<span data-ttu-id="e3c73-111">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e3c73-111">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
