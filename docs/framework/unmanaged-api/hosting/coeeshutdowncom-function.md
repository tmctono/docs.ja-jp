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
ms.openlocfilehash: 164384f043a1722ace6e5c4098cb31c4327cba1e
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2019
ms.locfileid: "70044071"
---
# <a name="coeeshutdowncom-function"></a><span data-ttu-id="85525-102">CoEEShutDownCOM 関数</span><span class="sxs-lookup"><span data-stu-id="85525-102">CoEEShutDownCOM Function</span></span>
<span data-ttu-id="85525-103">共通言語ランタイム (CLR) に対して、ランタイム呼び出し可能ラッパー (RCW) 内に保持されているすべてのインターフェイスポインターを強制的に解放します。</span><span class="sxs-lookup"><span data-stu-id="85525-103">Forces the common language runtime (CLR) to release all interface pointers it holds inside runtime callable wrappers (RCW).</span></span> <span data-ttu-id="85525-104">これにより、すべての RCW キャッシュが解放されます。</span><span class="sxs-lookup"><span data-stu-id="85525-104">This has the effect of releasing all RCW caches.</span></span> <span data-ttu-id="85525-105">このグローバル関数は .NET Framework 4 では非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="85525-105">This global function is deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="85525-106">代わりに、特定のランタイムのエントリポイントを使用します。</span><span class="sxs-lookup"><span data-stu-id="85525-106">Instead, use the entry point for a specific runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85525-107">構文</span><span class="sxs-lookup"><span data-stu-id="85525-107">Syntax</span></span>  
  
```cpp  
void CoEEShutDownCOM ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="85525-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="85525-108">Remarks</span></span>  
 <span data-ttu-id="85525-109">この`CoEEShutDownCOM`関数は、最初にすべてのコンテキストのすべての rcw とすべてのキャッシュを解放してから、セットアップに存在するすべての破棄通知を削除します。</span><span class="sxs-lookup"><span data-stu-id="85525-109">The `CoEEShutDownCOM` function first releases all the RCWs in all contexts and in all caches, and then removes any tear-down notification existing in setup.</span></span> <span data-ttu-id="85525-110">DLL のアンロードは行われません。</span><span class="sxs-lookup"><span data-stu-id="85525-110">No DLL unloading occurs.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="85525-111">この関数は、プロセスに読み込まれるすべてのランタイムに影響します。</span><span class="sxs-lookup"><span data-stu-id="85525-111">This function affects all runtimes that are loaded into the process.</span></span>  
  
 <span data-ttu-id="85525-112">.NET Framework 4 から、影響を与える特定のランタイムに対して、この関数のエントリポイントを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="85525-112">Beginning with the .NET Framework 4, call the entry point for this function on the specific runtime you want to affect.</span></span> <span data-ttu-id="85525-113">エントリポイントを取得するには、 [ICLRRuntimeInfo:: GetProcAddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md)メソッドを呼び出し、"Coees Tdowncom" を指定します。</span><span class="sxs-lookup"><span data-stu-id="85525-113">To get the entry point, call the [ICLRRuntimeInfo::GetProcAddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) method and specify "CoEEShutDownCOM".</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85525-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="85525-114">Requirements</span></span>  
 <span data-ttu-id="85525-115">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="85525-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85525-116">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="85525-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="85525-117">**ライブラリ**Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="85525-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="85525-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85525-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85525-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="85525-119">See also</span></span>

- [<span data-ttu-id="85525-120">メタデータ グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="85525-120">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
