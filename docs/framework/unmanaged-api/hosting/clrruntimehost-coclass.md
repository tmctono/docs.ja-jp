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
ms.openlocfilehash: 40766ce5837053493f2e3f1f25fe7d1d63ec695f
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616802"
---
# <a name="clrruntimehost-coclass"></a><span data-ttu-id="3bc69-102">CLRRuntimeHost コクラス</span><span class="sxs-lookup"><span data-stu-id="3bc69-102">CLRRuntimeHost Coclass</span></span>
<span data-ttu-id="3bc69-103">ランタイムによるコード実行を管理するためのインターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="3bc69-103">Provides interfaces for managing code execution by the runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bc69-104">構文</span><span class="sxs-lookup"><span data-stu-id="3bc69-104">Syntax</span></span>  
  
```cpp  
coclass CLRRuntimeHost {  
    [default] interface  ICLRRuntimeHost;  
    interface            ICLRValidator;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="3bc69-105">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3bc69-105">Interfaces</span></span>  
  
|<span data-ttu-id="3bc69-106">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3bc69-106">Interface</span></span>|<span data-ttu-id="3bc69-107">説明</span><span class="sxs-lookup"><span data-stu-id="3bc69-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="3bc69-108">ICLRRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3bc69-108">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)|<span data-ttu-id="3bc69-109">ランタイムによるアプリケーションの実行を制御するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="3bc69-109">Provides methods for controlling the execution of applications by the runtime.</span></span>|  
|[<span data-ttu-id="3bc69-110">ICLRValidator インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3bc69-110">ICLRValidator Interface</span></span>](iclrvalidator-interface.md)|<span data-ttu-id="3bc69-111">ポータブル実行可能イメージを検証し、検証エラーの詳細なレポートを作成するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="3bc69-111">Provides methods for validation of portable executable images and for detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3bc69-112">要件</span><span class="sxs-lookup"><span data-stu-id="3bc69-112">Requirements</span></span>  
 <span data-ttu-id="3bc69-113">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3bc69-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3bc69-114">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="3bc69-114">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="3bc69-115">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="3bc69-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3bc69-116">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3bc69-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bc69-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="3bc69-117">See also</span></span>

- [<span data-ttu-id="3bc69-118">ホスト コクラス</span><span class="sxs-lookup"><span data-stu-id="3bc69-118">Hosting Coclasses</span></span>](hosting-coclasses.md)
