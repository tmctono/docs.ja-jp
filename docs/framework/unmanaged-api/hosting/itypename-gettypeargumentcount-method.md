---
title: ITypeName::GetTypeArgumentCount メソッド
ms.date: 03/30/2017
api_name:
- ITypeName.GetTypeArgumentCount
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetTypeArgumentCount
helpviewer_keywords:
- GetTypeArgumentCount method [.NET Framework hosting]
- ITypeName::GetTypeArgumentCount method [.NET Framework hosting]
ms.assetid: ecb5480c-761a-4b02-83e0-b79abc67fd08
topic_type:
- apiref
ms.openlocfilehash: 627e4f596cde8f02edcaecfb26fa277b5ecf3a6b
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842141"
---
# <a name="itypenamegettypeargumentcount-method"></a><span data-ttu-id="23f9e-102">ITypeName::GetTypeArgumentCount メソッド</span><span class="sxs-lookup"><span data-stu-id="23f9e-102">ITypeName::GetTypeArgumentCount Method</span></span>
<span data-ttu-id="23f9e-103">このメソッドは、.NET Framework インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="23f9e-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23f9e-104">構文</span><span class="sxs-lookup"><span data-stu-id="23f9e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeArgumentCount (  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="23f9e-105">必要条件</span><span class="sxs-lookup"><span data-stu-id="23f9e-105">Requirements</span></span>  
 <span data-ttu-id="23f9e-106">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23f9e-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23f9e-107">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="23f9e-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="23f9e-108">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="23f9e-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="23f9e-109">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23f9e-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23f9e-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="23f9e-110">See also</span></span>

- [<span data-ttu-id="23f9e-111">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="23f9e-111">Hosting Interfaces</span></span>](hosting-interfaces.md)
