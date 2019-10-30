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
ms.openlocfilehash: 49a60b6b9b076138d8ff1f8a15041e9a6bacfede
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129252"
---
# <a name="iclrerrorreportingmanager-interface"></a><span data-ttu-id="9d87b-102">ICLRErrorReportingManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9d87b-102">ICLRErrorReportingManager Interface</span></span>
<span data-ttu-id="9d87b-103">エラー報告のためにホストがカスタムスタックダンプを構成できるようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="9d87b-103">Provides methods that allow the host to configure custom stack dumps for error reporting.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9d87b-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="9d87b-104">Methods</span></span>  
  
|<span data-ttu-id="9d87b-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="9d87b-105">Method</span></span>|<span data-ttu-id="9d87b-106">説明</span><span class="sxs-lookup"><span data-stu-id="9d87b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9d87b-107">BeginCustomDump メソッド</span><span class="sxs-lookup"><span data-stu-id="9d87b-107">BeginCustomDump Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md)|<span data-ttu-id="9d87b-108">エラー報告用のカスタムスタックダンプの構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="9d87b-108">Specifies the configuration of custom stack dumps for error reporting.</span></span>|  
|[<span data-ttu-id="9d87b-109">EndCustomDump メソッド</span><span class="sxs-lookup"><span data-stu-id="9d87b-109">EndCustomDump Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md)|<span data-ttu-id="9d87b-110">`BeginCustomDump`の以前の呼び出しで設定されたカスタムスタックダンプ構成をクリアします。</span><span class="sxs-lookup"><span data-stu-id="9d87b-110">Clears the custom stack dump configuration that was set by an earlier call to `BeginCustomDump`.</span></span>|  
|[<span data-ttu-id="9d87b-111">GetBucketParametersForCurrentException メソッド</span><span class="sxs-lookup"><span data-stu-id="9d87b-111">GetBucketParametersForCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-getbucketparametersforcurrentexception-method.md)|<span data-ttu-id="9d87b-112">呼び出し元のスレッドで現在の例外の Watson バケットを取得します。</span><span class="sxs-lookup"><span data-stu-id="9d87b-112">Gets the Watson bucket for the current exception on the calling thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9d87b-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="9d87b-113">Remarks</span></span>  
 <span data-ttu-id="9d87b-114">`BeginCustomDump` メソッドは、カスタムスタックダンプ構成を設定します。</span><span class="sxs-lookup"><span data-stu-id="9d87b-114">The `BeginCustomDump` method sets custom stack dump configuration.</span></span> <span data-ttu-id="9d87b-115">`EndCustomDump` メソッドは、カスタムスタックダンプ構成をクリアし、関連付けられているすべての状態を解放します。</span><span class="sxs-lookup"><span data-stu-id="9d87b-115">The `EndCustomDump` method clears the custom stack dump configuration and frees any associated state.</span></span> <span data-ttu-id="9d87b-116">カスタムダンプの完了後に呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d87b-116">It should be called after the custom dump is complete.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="9d87b-117">`EndCustomDump` を呼び出さないと、メモリがリークします。</span><span class="sxs-lookup"><span data-stu-id="9d87b-117">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d87b-118">［要件］</span><span class="sxs-lookup"><span data-stu-id="9d87b-118">Requirements</span></span>  
 <span data-ttu-id="9d87b-119">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d87b-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d87b-120">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="9d87b-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9d87b-121">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="9d87b-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9d87b-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d87b-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d87b-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="9d87b-123">See also</span></span>

- [<span data-ttu-id="9d87b-124">ECustomDumpItemKind 列挙型</span><span class="sxs-lookup"><span data-stu-id="9d87b-124">ECustomDumpItemKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)
- [<span data-ttu-id="9d87b-125">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9d87b-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
