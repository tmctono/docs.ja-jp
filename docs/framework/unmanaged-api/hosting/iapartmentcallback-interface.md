---
title: IApartmentCallback インターフェイス
ms.date: 03/30/2017
api_name:
- IApartmentCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IApartmentCallback
helpviewer_keywords:
- IApartmentCallback interface [.NET Framework hosting]
ms.assetid: 57c33c58-bf0b-4533-b569-e6a682d02cba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: db933716cc0602ecda5da8a72726408ae4910179
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59129806"
---
# <a name="iapartmentcallback-interface"></a><span data-ttu-id="ca5c0-102">IApartmentCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ca5c0-102">IApartmentCallback Interface</span></span>
<span data-ttu-id="ca5c0-103">アパートメント内でのコールバックを行うためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="ca5c0-103">Provides methods for making callbacks within an apartment.</span></span> <span data-ttu-id="ca5c0-104">*アパートメント*は同じスレッドへのアクセス要件を共有するオブジェクトのプロセス内の論理コンテナーです。</span><span class="sxs-lookup"><span data-stu-id="ca5c0-104">An *apartment* is a logical container within a process for objects that share the same thread access requirements.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ca5c0-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="ca5c0-105">Methods</span></span>  
  
|<span data-ttu-id="ca5c0-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="ca5c0-106">Method</span></span>|<span data-ttu-id="ca5c0-107">説明</span><span class="sxs-lookup"><span data-stu-id="ca5c0-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ca5c0-108">DoCallback メソッド</span><span class="sxs-lookup"><span data-stu-id="ca5c0-108">DoCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-docallback-method.md)|<span data-ttu-id="ca5c0-109">アパートメント内で指定された関数を実行します。</span><span class="sxs-lookup"><span data-stu-id="ca5c0-109">Executes the specified function within an apartment.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ca5c0-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="ca5c0-110">Requirements</span></span>  
 <span data-ttu-id="ca5c0-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca5c0-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca5c0-112">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ca5c0-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ca5c0-113">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="ca5c0-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="ca5c0-114">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="ca5c0-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ca5c0-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="ca5c0-115">See also</span></span>

- [<span data-ttu-id="ca5c0-116">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ca5c0-116">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
