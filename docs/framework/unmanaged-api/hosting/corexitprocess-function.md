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
ms.openlocfilehash: 2a28b33f80299ae6fce34f9de66b6f7f1bc70ef6
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490564"
---
# <a name="corexitprocess-function"></a><span data-ttu-id="fb828-102">CorExitProcess 関数</span><span class="sxs-lookup"><span data-stu-id="fb828-102">CorExitProcess Function</span></span>
<span data-ttu-id="fb828-103">現在のアンマネージ プロセスを終了します。</span><span class="sxs-lookup"><span data-stu-id="fb828-103">Shuts down the current unmanaged process.</span></span>  
  
 <span data-ttu-id="fb828-104">この関数は、.NET Framework 4 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="fb828-104">This function has been deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="fb828-105">使用して、 [iclrmetahost::exitprocess](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md)メソッド代わりにします。</span><span class="sxs-lookup"><span data-stu-id="fb828-105">Use the [ICLRMetaHost::ExitProcess](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb828-106">構文</span><span class="sxs-lookup"><span data-stu-id="fb828-106">Syntax</span></span>  
  
```  
void STDMETHODCALLTYPE CorExitProcess (   
  int  exitCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fb828-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fb828-107">Parameters</span></span>  
 `exitCode`  
 <span data-ttu-id="fb828-108">プロセス終了コードを指定する整数。</span><span class="sxs-lookup"><span data-stu-id="fb828-108">An integer that specifies the process exit code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb828-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="fb828-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fb828-110">以降、.NET Framework 4 で`CorExitProcess`従来の Api がバインドされているランタイムだけでなく、プロセスの開始ごとランタイムが終了します。</span><span class="sxs-lookup"><span data-stu-id="fb828-110">Beginning with the .NET Framework 4, `CorExitProcess` exits every started runtime in the process, not just the runtime to which the legacy APIs have been bound.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb828-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="fb828-111">Requirements</span></span>  
 <span data-ttu-id="fb828-112">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb828-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb828-113">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fb828-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fb828-114">**ライブラリ:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fb828-114">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fb828-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb828-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb828-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="fb828-116">See also</span></span>

- [<span data-ttu-id="fb828-117">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="fb828-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
