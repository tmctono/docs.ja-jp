---
title: CLRRuntimeHost コクラス
ms.date: 03/30/2017
api_name:
- CLRRuntimeHost Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CLRRuntimeHost
helpviewer_keywords:
- CLRRuntimeHost coclass [.NET Framework hosting]
ms.assetid: 2ac9cbf5-8a2d-4e4f-8831-0dad8ef0a897
topic_type:
- apiref
ms.openlocfilehash: b1e595e1a4f1b462437f47207b998829a8bd774d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129460"
---
# <a name="clrruntimehost-coclass"></a><span data-ttu-id="f60be-102">CLRRuntimeHost コクラス</span><span class="sxs-lookup"><span data-stu-id="f60be-102">CLRRuntimeHost Coclass</span></span>
<span data-ttu-id="f60be-103">ランタイムによるコード実行を管理するためのインターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="f60be-103">Provides interfaces for managing code execution by the runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f60be-104">構文</span><span class="sxs-lookup"><span data-stu-id="f60be-104">Syntax</span></span>  
  
```cpp  
coclass CLRRuntimeHost {  
    [default] interface  ICLRRuntimeHost;  
    interface            ICLRValidator;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="f60be-105">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f60be-105">Interfaces</span></span>  
  
|<span data-ttu-id="f60be-106">Interface</span><span class="sxs-lookup"><span data-stu-id="f60be-106">Interface</span></span>|<span data-ttu-id="f60be-107">説明</span><span class="sxs-lookup"><span data-stu-id="f60be-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="f60be-108">ICLRRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f60be-108">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)|<span data-ttu-id="f60be-109">ランタイムによるアプリケーションの実行を制御するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="f60be-109">Provides methods for controlling the execution of applications by the runtime.</span></span>|  
|[<span data-ttu-id="f60be-110">ICLRValidator インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f60be-110">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)|<span data-ttu-id="f60be-111">ポータブル実行可能イメージを検証し、検証エラーの詳細なレポートを作成するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="f60be-111">Provides methods for validation of portable executable images and for detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f60be-112">［要件］</span><span class="sxs-lookup"><span data-stu-id="f60be-112">Requirements</span></span>  
 <span data-ttu-id="f60be-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f60be-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f60be-114">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="f60be-114">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="f60be-115">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="f60be-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f60be-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f60be-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f60be-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="f60be-117">See also</span></span>

- [<span data-ttu-id="f60be-118">ホスト コクラス</span><span class="sxs-lookup"><span data-stu-id="f60be-118">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
