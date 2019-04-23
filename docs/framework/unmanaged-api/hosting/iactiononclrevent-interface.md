---
title: IActionOnCLREvent インターフェイス
ms.date: 03/30/2017
api_name:
- IActionOnCLREvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IActionOnCLREvent
helpviewer_keywords:
- IActionOnCLREvent interface [.NET Framework hosting]
ms.assetid: b5f9b41e-7301-429c-911f-21d5422292b3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 864a8a4dd9f96da2fd0e0025848a910b4f8b0a70
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59180521"
---
# <a name="iactiononclrevent-interface"></a><span data-ttu-id="c5bdd-102">IActionOnCLREvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c5bdd-102">IActionOnCLREvent Interface</span></span>
<span data-ttu-id="c5bdd-103">提供、 [iactiononclrevent::onevent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md)への呼び出しを使用して登録されているイベントのコールバックを実行するメソッドに、 [iclroneventmanager::registeractiononevent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="c5bdd-103">Provides the [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) method, which performs callbacks on events that have been registered by using a call to the [ICLROnEventManager::RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c5bdd-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="c5bdd-104">Methods</span></span>  
  
|<span data-ttu-id="c5bdd-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="c5bdd-105">Method</span></span>|<span data-ttu-id="c5bdd-106">説明</span><span class="sxs-lookup"><span data-stu-id="c5bdd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c5bdd-107">OnEvent メソッド</span><span class="sxs-lookup"><span data-stu-id="c5bdd-107">OnEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md)|<span data-ttu-id="c5bdd-108">登録済みのイベントのコールバックを実行します。</span><span class="sxs-lookup"><span data-stu-id="c5bdd-108">Performs a callback for a registered event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c5bdd-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="c5bdd-109">Requirements</span></span>  
 <span data-ttu-id="c5bdd-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5bdd-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5bdd-111">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c5bdd-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c5bdd-112">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="c5bdd-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c5bdd-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5bdd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5bdd-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="c5bdd-114">See also</span></span>

- [<span data-ttu-id="c5bdd-115">EClrEvent 列挙型</span><span class="sxs-lookup"><span data-stu-id="c5bdd-115">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [<span data-ttu-id="c5bdd-116">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c5bdd-116">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="c5bdd-117">ICLROnEventManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c5bdd-117">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
- [<span data-ttu-id="c5bdd-118">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c5bdd-118">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
