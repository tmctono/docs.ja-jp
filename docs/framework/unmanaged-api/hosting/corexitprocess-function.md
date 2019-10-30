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
ms.openlocfilehash: fe61503cdf46b6b2cf568deb78b96f8fa885c203
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136932"
---
# <a name="corexitprocess-function"></a><span data-ttu-id="f0483-102">CorExitProcess 関数</span><span class="sxs-lookup"><span data-stu-id="f0483-102">CorExitProcess Function</span></span>
<span data-ttu-id="f0483-103">現在のアンマネージ プロセスを終了します。</span><span class="sxs-lookup"><span data-stu-id="f0483-103">Shuts down the current unmanaged process.</span></span>  
  
 <span data-ttu-id="f0483-104">この関数は .NET Framework 4 で非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="f0483-104">This function has been deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="f0483-105">代わりに[ICLRMetaHost:: ExitProcess](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md)メソッドを使用してください。</span><span class="sxs-lookup"><span data-stu-id="f0483-105">Use the [ICLRMetaHost::ExitProcess](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0483-106">構文</span><span class="sxs-lookup"><span data-stu-id="f0483-106">Syntax</span></span>  
  
```cpp  
void STDMETHODCALLTYPE CorExitProcess (   
  int  exitCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0483-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f0483-107">Parameters</span></span>  
 `exitCode`  
 <span data-ttu-id="f0483-108">プロセス終了コードを指定する整数です。</span><span class="sxs-lookup"><span data-stu-id="f0483-108">An integer that specifies the process exit code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0483-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="f0483-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f0483-110">.NET Framework 4 以降では、レガシ Api がバインドされているランタイムだけでなく、プロセスで開始されたすべてのランタイムを終了 `CorExitProcess` ます。</span><span class="sxs-lookup"><span data-stu-id="f0483-110">Beginning with the .NET Framework 4, `CorExitProcess` exits every started runtime in the process, not just the runtime to which the legacy APIs have been bound.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0483-111">［要件］</span><span class="sxs-lookup"><span data-stu-id="f0483-111">Requirements</span></span>  
 <span data-ttu-id="f0483-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0483-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0483-113">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="f0483-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f0483-114">**ライブラリ:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="f0483-114">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f0483-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0483-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0483-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="f0483-116">See also</span></span>

- [<span data-ttu-id="f0483-117">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="f0483-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
