---
title: ITypeNameFactory::ParseTypeName メソッド
ms.date: 03/30/2017
api_name:
- ITypeNameFactory.ParseTypeName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ParseTypeName
helpviewer_keywords:
- ITypeNameFactory::ParseTypeName method [.NET Framework hosting]
- ParseTypeName method [.NET Framework hosting]
ms.assetid: 13c9f063-371c-4911-a5e7-e1e0b88ae382
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cbe5f634a5d0580c7e58b03f318da98a0112fa6b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59208086"
---
# <a name="itypenamefactoryparsetypename-method"></a><span data-ttu-id="1ea76-102">ITypeNameFactory::ParseTypeName メソッド</span><span class="sxs-lookup"><span data-stu-id="1ea76-102">ITypeNameFactory::ParseTypeName Method</span></span>
<span data-ttu-id="1ea76-103">このメソッドは、.NET Framework インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="1ea76-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ea76-104">構文</span><span class="sxs-lookup"><span data-stu-id="1ea76-104">Syntax</span></span>  
  
```  
HRESULT ParseTypeName (  
    [in]  LPCWSTR             szName,  
    [out] DWORD*              pError,  
    [out, retval] ITypeName** ppTypeName  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="1ea76-105">必要条件</span><span class="sxs-lookup"><span data-stu-id="1ea76-105">Requirements</span></span>  
 <span data-ttu-id="1ea76-106">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ea76-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ea76-107">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1ea76-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1ea76-108">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="1ea76-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1ea76-109">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ea76-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ea76-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="1ea76-110">See also</span></span>

- [<span data-ttu-id="1ea76-111">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1ea76-111">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
