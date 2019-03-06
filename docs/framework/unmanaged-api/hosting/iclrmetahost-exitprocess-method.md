---
title: ICLRMetaHost::ExitProcess メソッド
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.ExitProcess
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::ExitProcess
helpviewer_keywords:
- ICLRMetaHost::ExitProcess method [.NET Framework hosting]
- ExitProcess method, ICLRMetaHost interface [.NET Framework hosting]
ms.assetid: b4df98cc-4e4e-407b-b8f4-e0076afef3a4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eed86f37ccab2d7eefead4997362fb82d310a1d1
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57502377"
---
# <a name="iclrmetahostexitprocess-method"></a><span data-ttu-id="70675-102">ICLRMetaHost::ExitProcess メソッド</span><span class="sxs-lookup"><span data-stu-id="70675-102">ICLRMetaHost::ExitProcess Method</span></span>
<span data-ttu-id="70675-103">すべての読み込まれたランタイムを適切にシャット ダウンしようとしてのプロセスを終了します。</span><span class="sxs-lookup"><span data-stu-id="70675-103">Attempts to shut down all loaded runtimes gracefully and then terminates the process.</span></span> <span data-ttu-id="70675-104">も優先されます、 [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md)関数。</span><span class="sxs-lookup"><span data-stu-id="70675-104">Supersedes the [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70675-105">構文</span><span class="sxs-lookup"><span data-stu-id="70675-105">Syntax</span></span>  
  
```  
HRESULT ExitProcess (  
    [in] INT32 iExitCode);  
```  
  
## <a name="parameters"></a><span data-ttu-id="70675-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="70675-106">Parameters</span></span>  
 `iExitCode`  
 <span data-ttu-id="70675-107">[in]プロセスの終了コード。</span><span class="sxs-lookup"><span data-stu-id="70675-107">[in] The exit code for the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="70675-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="70675-108">Return Value</span></span>  
 <span data-ttu-id="70675-109">このメソッド、その戻り値が定義されていないためです。</span><span class="sxs-lookup"><span data-stu-id="70675-109">This method never returns, so its return value is undefined.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="70675-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="70675-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70675-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="70675-111">Requirements</span></span>  
 <span data-ttu-id="70675-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="70675-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70675-113">**ヘッダー:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="70675-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="70675-114">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="70675-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="70675-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70675-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70675-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="70675-116">See also</span></span>
- [<span data-ttu-id="70675-117">ICLRMetaHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="70675-117">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="70675-118">ホスティング</span><span class="sxs-lookup"><span data-stu-id="70675-118">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
