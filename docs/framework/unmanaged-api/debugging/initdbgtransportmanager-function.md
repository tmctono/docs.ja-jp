---
title: InitDbgTransportManager 関数
ms.date: 03/30/2017
api_name:
- InitDbgTransportManager
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- InitDbgTransportManager
helpviewer_keywords:
- remote debugging API [Silverlight]
- InitDbgTransportManager function
- Silverlight, remote debugging
ms.assetid: a30102ff-c52e-48c9-b3a9-aa14286a42b2
topic_type:
- apiref
ms.openlocfilehash: e18ceb25b9c58a9710ef967cb071e3ef55beea8c
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421047"
---
# <a name="initdbgtransportmanager-function"></a><span data-ttu-id="eed76-102">InitDbgTransportManager 関数</span><span class="sxs-lookup"><span data-stu-id="eed76-102">InitDbgTransportManager Function</span></span>
<span data-ttu-id="eed76-103">プロセスおよびランタイムの列挙のためにリモート ターゲットに接続するよう、トランスポート マネージャーを初期化します。</span><span class="sxs-lookup"><span data-stu-id="eed76-103">Initializes the transport manager to connect to a remote target for process and runtime enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eed76-104">構文</span><span class="sxs-lookup"><span data-stu-id="eed76-104">Syntax</span></span>  
  
```cpp  
HRESULT InitDbgTransportManager ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="eed76-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="eed76-105">Return Value</span></span>  
 <span data-ttu-id="eed76-106">S_OK</span><span class="sxs-lookup"><span data-stu-id="eed76-106">S_OK</span></span>  
 <span data-ttu-id="eed76-107">成功しました。</span><span class="sxs-lookup"><span data-stu-id="eed76-107">Success.</span></span>  
  
 <span data-ttu-id="eed76-108">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="eed76-108">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="eed76-109">関数はトランスポート マネージャーにメモリを割り当てられませんでした。</span><span class="sxs-lookup"><span data-stu-id="eed76-109">The function was unable to allocate memory for a transport manager.</span></span>  
  
 <span data-ttu-id="eed76-110">E_FAIL (またはその他の E_ リターン コード)</span><span class="sxs-lookup"><span data-stu-id="eed76-110">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="eed76-111">その他のエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="eed76-111">Other failures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eed76-112">要件</span><span class="sxs-lookup"><span data-stu-id="eed76-112">Requirements</span></span>  
 <span data-ttu-id="eed76-113">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eed76-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eed76-114">**ヘッダー:** Coreclrremoteデバッグインターフェイス .h</span><span class="sxs-lookup"><span data-stu-id="eed76-114">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="eed76-115">**Library:** mscordbi_macx86 .dll</span><span class="sxs-lookup"><span data-stu-id="eed76-115">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="eed76-116">**.NET Framework のバージョン:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="eed76-116">**.NET Framework Versions:** 3.5 SP1</span></span>
