---
title: CoEEShutDownCOM 関数
ms.date: 03/30/2017
api_name:
- CoEEShutDownCOM
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoEEShutDownCOM
helpviewer_keywords:
- CoEEShutDownCOM function [.NET Framework hosting]
ms.assetid: b634cae2-632f-4737-9be4-92d0652844d7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6a28b9d6e41d0572d423576f5b4024a60a70216c
ms.sourcegitcommit: 518e7634b86d3980ec7da5f8c308cc1054daedb7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2019
ms.locfileid: "66456867"
---
# <a name="coeeshutdowncom-function"></a><span data-ttu-id="4363a-102">CoEEShutDownCOM 関数</span><span class="sxs-lookup"><span data-stu-id="4363a-102">CoEEShutDownCOM Function</span></span>
<span data-ttu-id="4363a-103">共通言語ランタイム (CLR) がランタイム呼び出し可能ラッパー (RCW) 内で保持しているすべてのインターフェイス ポインターを解放するを強制します。</span><span class="sxs-lookup"><span data-stu-id="4363a-103">Forces the common language runtime (CLR) to release all interface pointers it holds inside runtime callable wrappers (RCW).</span></span> <span data-ttu-id="4363a-104">RCW のすべてのキャッシュの解放の効果があります。</span><span class="sxs-lookup"><span data-stu-id="4363a-104">This has the effect of releasing all RCW caches.</span></span> <span data-ttu-id="4363a-105">このグローバル関数は非推奨、[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="4363a-105">This global function is deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="4363a-106">代わりに、特定のランタイムのエントリ ポイントを使用します。</span><span class="sxs-lookup"><span data-stu-id="4363a-106">Instead, use the entry point for a specific runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4363a-107">構文</span><span class="sxs-lookup"><span data-stu-id="4363a-107">Syntax</span></span>  
  
```  
void CoEEShutDownCOM ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="4363a-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="4363a-108">Remarks</span></span>  
 <span data-ttu-id="4363a-109">`CoEEShutDownCOM`関数が最初にすべてのコンテキスト内とすべてのキャッシュにあるすべての Rcw を解放し、し、セットアップで既存の任意の終了処理通知を削除します。</span><span class="sxs-lookup"><span data-stu-id="4363a-109">The `CoEEShutDownCOM` function first releases all the RCWs in all contexts and in all caches, and then removes any tear-down notification existing in setup.</span></span> <span data-ttu-id="4363a-110">DLL のアンロードは行われません。</span><span class="sxs-lookup"><span data-stu-id="4363a-110">No DLL unloading occurs.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="4363a-111">この関数では、プロセスに読み込まれるすべてのランタイムに影響します。</span><span class="sxs-lookup"><span data-stu-id="4363a-111">This function affects all runtimes that are loaded into the process.</span></span>  
  
 <span data-ttu-id="4363a-112">以降、.NET Framework 4 では、この関数に影響する特定のランタイムのエントリ ポイントを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4363a-112">Beginning with the .NET Framework 4, call the entry point for this function on the specific runtime you want to affect.</span></span> <span data-ttu-id="4363a-113">エントリ ポイントを取得する、 [iclrruntimeinfo::getprocaddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md)メソッド"CoEEShutDownCOM"を指定します。</span><span class="sxs-lookup"><span data-stu-id="4363a-113">To get the entry point, call the [ICLRRuntimeInfo::GetProcAddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) method and specify "CoEEShutDownCOM".</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4363a-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="4363a-114">Requirements</span></span>  
 <span data-ttu-id="4363a-115">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4363a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4363a-116">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4363a-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4363a-117">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="4363a-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4363a-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4363a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4363a-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="4363a-119">See also</span></span>

- [<span data-ttu-id="4363a-120">メタデータ グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="4363a-120">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
