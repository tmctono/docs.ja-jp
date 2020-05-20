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
ms.openlocfilehash: a60805e1fd78cb14835957a7afc14fe279cb20fb
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616568"
---
# <a name="corexitprocess-function"></a><span data-ttu-id="a6d45-102">CorExitProcess 関数</span><span class="sxs-lookup"><span data-stu-id="a6d45-102">CorExitProcess Function</span></span>
<span data-ttu-id="a6d45-103">現在のアンマネージ プロセスを終了します。</span><span class="sxs-lookup"><span data-stu-id="a6d45-103">Shuts down the current unmanaged process.</span></span>  
  
 <span data-ttu-id="a6d45-104">この関数は .NET Framework 4 で非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="a6d45-104">This function has been deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="a6d45-105">代わりに[ICLRMetaHost:: ExitProcess](iclrmetahost-exitprocess-method.md)メソッドを使用してください。</span><span class="sxs-lookup"><span data-stu-id="a6d45-105">Use the [ICLRMetaHost::ExitProcess](iclrmetahost-exitprocess-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6d45-106">構文</span><span class="sxs-lookup"><span data-stu-id="a6d45-106">Syntax</span></span>  
  
```cpp  
void STDMETHODCALLTYPE CorExitProcess (
  int  exitCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6d45-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a6d45-107">Parameters</span></span>  
 `exitCode`  
 <span data-ttu-id="a6d45-108">プロセス終了コードを指定する整数です。</span><span class="sxs-lookup"><span data-stu-id="a6d45-108">An integer that specifies the process exit code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a6d45-109">解説</span><span class="sxs-lookup"><span data-stu-id="a6d45-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a6d45-110">.NET Framework 4 以降では、 `CorExitProcess` レガシ api がバインドされているランタイムだけでなく、プロセスで開始されたすべてのランタイムを終了します。</span><span class="sxs-lookup"><span data-stu-id="a6d45-110">Beginning with the .NET Framework 4, `CorExitProcess` exits every started runtime in the process, not just the runtime to which the legacy APIs have been bound.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6d45-111">要件</span><span class="sxs-lookup"><span data-stu-id="a6d45-111">Requirements</span></span>  
 <span data-ttu-id="a6d45-112">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6d45-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6d45-113">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="a6d45-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a6d45-114">**ライブラリ:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="a6d45-114">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a6d45-115">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6d45-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6d45-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="a6d45-116">See also</span></span>

- [<span data-ttu-id="a6d45-117">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="a6d45-117">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
