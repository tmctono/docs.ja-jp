---
title: ITypeName::GetModifiers メソッド
ms.date: 03/30/2017
api_name:
- ITypeName.GetModifiers
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetModifiers
helpviewer_keywords:
- ITypeName::GetModifiers method [.NET Framework hosting]
- GetModifiers method [.NET Framework hosting]
ms.assetid: 75508c55-3e09-4135-80da-cc811003fa82
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 15804673733ffba7e65c3d280cdc87a76739aaed
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67748990"
---
# <a name="itypenamegetmodifiers-method"></a><span data-ttu-id="c1309-102">ITypeName::GetModifiers メソッド</span><span class="sxs-lookup"><span data-stu-id="c1309-102">ITypeName::GetModifiers Method</span></span>
<span data-ttu-id="c1309-103">このメソッドは、.NET Framework インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="c1309-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1309-104">構文</span><span class="sxs-lookup"><span data-stu-id="c1309-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModifiers (  
    [in] DWORD           count,  
    [out] DWORD*         rgModifiers,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="c1309-105">必要条件</span><span class="sxs-lookup"><span data-stu-id="c1309-105">Requirements</span></span>  
 <span data-ttu-id="c1309-106">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1309-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1309-107">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c1309-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c1309-108">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="c1309-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c1309-109">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1309-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1309-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="c1309-110">See also</span></span>

- [<span data-ttu-id="c1309-111">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c1309-111">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
