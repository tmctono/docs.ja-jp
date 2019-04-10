---
title: CorExitProcess 関数
ms.date: 03/30/2017
api_name:
- CorExitProcess
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CorExitProcess
helpviewer_keywords:
- CorExitProcess function [.NET Framework hosting]
ms.assetid: a5cab4c6-990e-47f3-8798-cf422b791015
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b95625cfe17b36c0244e6780a08dcf50ce50763d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59201859"
---
# <a name="corexitprocess-function"></a><span data-ttu-id="07f83-102">CorExitProcess 関数</span><span class="sxs-lookup"><span data-stu-id="07f83-102">CorExitProcess Function</span></span>
<span data-ttu-id="07f83-103">現在のアンマネージ プロセスを終了します。</span><span class="sxs-lookup"><span data-stu-id="07f83-103">Shuts down the current unmanaged process.</span></span>  
  
 <span data-ttu-id="07f83-104">この関数は、[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] では非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="07f83-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="07f83-105">使用して、 [iclrmetahost::exitprocess](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md)メソッド代わりにします。</span><span class="sxs-lookup"><span data-stu-id="07f83-105">Use the [ICLRMetaHost::ExitProcess](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07f83-106">構文</span><span class="sxs-lookup"><span data-stu-id="07f83-106">Syntax</span></span>  
  
```  
void STDMETHODCALLTYPE CorExitProcess (   
  int  exitCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="07f83-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="07f83-107">Parameters</span></span>  
 `exitCode`  
 <span data-ttu-id="07f83-108">プロセス終了コードを指定する整数。</span><span class="sxs-lookup"><span data-stu-id="07f83-108">An integer that specifies the process exit code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="07f83-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="07f83-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="07f83-110">以降では、 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]、`CorExitProcess`従来の Api がバインドされているランタイムだけでなく、プロセスの開始ごとランタイムが終了します。</span><span class="sxs-lookup"><span data-stu-id="07f83-110">Beginning with the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], `CorExitProcess` exits every started runtime in the process, not just the runtime to which the legacy APIs have been bound.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07f83-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="07f83-111">Requirements</span></span>  
 <span data-ttu-id="07f83-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="07f83-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07f83-113">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="07f83-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="07f83-114">**ライブラリ:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="07f83-114">**Library:** MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="07f83-115">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="07f83-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="07f83-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="07f83-116">See also</span></span>

- [<span data-ttu-id="07f83-117">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="07f83-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
