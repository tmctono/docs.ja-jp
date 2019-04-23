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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8bae2d134c412023d0f126453b5285662d994c78
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59207761"
---
# <a name="clrruntimehost-coclass"></a><span data-ttu-id="629db-102">CLRRuntimeHost コクラス</span><span class="sxs-lookup"><span data-stu-id="629db-102">CLRRuntimeHost Coclass</span></span>
<span data-ttu-id="629db-103">ランタイムによってコードが実行を管理するためのインターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="629db-103">Provides interfaces for managing code execution by the runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="629db-104">構文</span><span class="sxs-lookup"><span data-stu-id="629db-104">Syntax</span></span>  
  
```  
coclass CLRRuntimeHost {  
    [default] interface  ICLRRuntimeHost;  
    interface            ICLRValidator;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="629db-105">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="629db-105">Interfaces</span></span>  
  
|<span data-ttu-id="629db-106">Interface</span><span class="sxs-lookup"><span data-stu-id="629db-106">Interface</span></span>|<span data-ttu-id="629db-107">説明</span><span class="sxs-lookup"><span data-stu-id="629db-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="629db-108">ICLRRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="629db-108">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)|<span data-ttu-id="629db-109">ランタイムによってアプリケーションの実行を制御するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="629db-109">Provides methods for controlling the execution of applications by the runtime.</span></span>|  
|[<span data-ttu-id="629db-110">ICLRValidator インターフェイス</span><span class="sxs-lookup"><span data-stu-id="629db-110">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)|<span data-ttu-id="629db-111">ポータブル実行可能イメージの検証し、検証エラーの詳細なレポートのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="629db-111">Provides methods for validation of portable executable images and for detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="629db-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="629db-112">Requirements</span></span>  
 <span data-ttu-id="629db-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="629db-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="629db-114">**ヘッダー:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="629db-114">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="629db-115">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="629db-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="629db-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="629db-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="629db-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="629db-117">See also</span></span>

- [<span data-ttu-id="629db-118">ホスト コクラス</span><span class="sxs-lookup"><span data-stu-id="629db-118">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
