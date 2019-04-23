---
title: ITypeName::GetTypeArguments メソッド
ms.date: 03/30/2017
api_name:
- ITypeName.GetTypeArguments
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetTypeArguments
helpviewer_keywords:
- ITypeName::GetTypeArguments method [.NET Framework hosting]
- GetTypeArguments method [.NET Framework hosting]
ms.assetid: 638d77df-ff9c-40d9-88ee-930f5f87ada1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e4cd4fa8f4ba2bea5a2a853544eae6239bfaaeba
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59132276"
---
# <a name="itypenamegettypearguments-method"></a><span data-ttu-id="55e37-102">ITypeName::GetTypeArguments メソッド</span><span class="sxs-lookup"><span data-stu-id="55e37-102">ITypeName::GetTypeArguments Method</span></span>
<span data-ttu-id="55e37-103">このメソッドは、.NET Framework インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="55e37-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55e37-104">構文</span><span class="sxs-lookup"><span data-stu-id="55e37-104">Syntax</span></span>  
  
```  
HRESULT GetTypeArguments (  
    [in] DWORD           count,  
    [out] ITypeName**    rgpArguments,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="55e37-105">必要条件</span><span class="sxs-lookup"><span data-stu-id="55e37-105">Requirements</span></span>  
 <span data-ttu-id="55e37-106">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="55e37-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55e37-107">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="55e37-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="55e37-108">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="55e37-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="55e37-109">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55e37-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55e37-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="55e37-110">See also</span></span>

- [<span data-ttu-id="55e37-111">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="55e37-111">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
