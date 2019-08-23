---
title: ICLRErrorReportingManager インターフェイス
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager
helpviewer_keywords:
- ICLRErrorReportingManager interface [.NET Framework hosting]
ms.assetid: ea8af0d5-4133-4472-8a1f-50570d7e85fa
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2a9d9cff0360e4eb27584fe0f22c1c20396ff8f0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966258"
---
# <a name="iclrerrorreportingmanager-interface"></a><span data-ttu-id="7268c-102">ICLRErrorReportingManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7268c-102">ICLRErrorReportingManager Interface</span></span>
<span data-ttu-id="7268c-103">エラー報告のためにホストがカスタムスタックダンプを構成できるようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="7268c-103">Provides methods that allow the host to configure custom stack dumps for error reporting.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7268c-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="7268c-104">Methods</span></span>  
  
|<span data-ttu-id="7268c-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="7268c-105">Method</span></span>|<span data-ttu-id="7268c-106">説明</span><span class="sxs-lookup"><span data-stu-id="7268c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7268c-107">BeginCustomDump メソッド</span><span class="sxs-lookup"><span data-stu-id="7268c-107">BeginCustomDump Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md)|<span data-ttu-id="7268c-108">エラー報告用のカスタムスタックダンプの構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="7268c-108">Specifies the configuration of custom stack dumps for error reporting.</span></span>|  
|[<span data-ttu-id="7268c-109">EndCustomDump メソッド</span><span class="sxs-lookup"><span data-stu-id="7268c-109">EndCustomDump Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md)|<span data-ttu-id="7268c-110">以前のの呼び出し`BeginCustomDump`で設定されたカスタムスタックダンプ構成を消去します。</span><span class="sxs-lookup"><span data-stu-id="7268c-110">Clears the custom stack dump configuration that was set by an earlier call to `BeginCustomDump`.</span></span>|  
|[<span data-ttu-id="7268c-111">GetBucketParametersForCurrentException メソッド</span><span class="sxs-lookup"><span data-stu-id="7268c-111">GetBucketParametersForCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-getbucketparametersforcurrentexception-method.md)|<span data-ttu-id="7268c-112">呼び出し元のスレッドで現在の例外の Watson バケットを取得します。</span><span class="sxs-lookup"><span data-stu-id="7268c-112">Gets the Watson bucket for the current exception on the calling thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7268c-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="7268c-113">Remarks</span></span>  
 <span data-ttu-id="7268c-114">メソッド`BeginCustomDump`は、カスタムスタックダンプ構成を設定します。</span><span class="sxs-lookup"><span data-stu-id="7268c-114">The `BeginCustomDump` method sets custom stack dump configuration.</span></span> <span data-ttu-id="7268c-115">メソッド`EndCustomDump`は、カスタムスタックダンプ構成をクリアし、関連付けられているすべての状態を解放します。</span><span class="sxs-lookup"><span data-stu-id="7268c-115">The `EndCustomDump` method clears the custom stack dump configuration and frees any associated state.</span></span> <span data-ttu-id="7268c-116">カスタムダンプの完了後に呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="7268c-116">It should be called after the custom dump is complete.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="7268c-117">を呼び出さ`EndCustomDump`ないと、メモリがリークします。</span><span class="sxs-lookup"><span data-stu-id="7268c-117">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7268c-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="7268c-118">Requirements</span></span>  
 <span data-ttu-id="7268c-119">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7268c-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7268c-120">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="7268c-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7268c-121">**ライブラリ**Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="7268c-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7268c-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7268c-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7268c-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="7268c-123">See also</span></span>

- [<span data-ttu-id="7268c-124">ECustomDumpItemKind 列挙型</span><span class="sxs-lookup"><span data-stu-id="7268c-124">ECustomDumpItemKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)
- [<span data-ttu-id="7268c-125">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7268c-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
