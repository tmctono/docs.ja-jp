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
ms.openlocfilehash: 2d67bee3ea0e57080179b3fbb7e0b4193860c44d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73103286"
---
# <a name="initdbgtransportmanager-function"></a><span data-ttu-id="f7792-102">InitDbgTransportManager 関数</span><span class="sxs-lookup"><span data-stu-id="f7792-102">InitDbgTransportManager Function</span></span>
<span data-ttu-id="f7792-103">プロセスおよびランタイムの列挙のためにリモート ターゲットに接続するよう、トランスポート マネージャーを初期化します。</span><span class="sxs-lookup"><span data-stu-id="f7792-103">Initializes the transport manager to connect to a remote target for process and runtime enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7792-104">構文</span><span class="sxs-lookup"><span data-stu-id="f7792-104">Syntax</span></span>  
  
```cpp  
HRESULT InitDbgTransportManager ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="f7792-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="f7792-105">Return Value</span></span>  
 <span data-ttu-id="f7792-106">S_OK</span><span class="sxs-lookup"><span data-stu-id="f7792-106">S_OK</span></span>  
 <span data-ttu-id="f7792-107">成功。</span><span class="sxs-lookup"><span data-stu-id="f7792-107">Success.</span></span>  
  
 <span data-ttu-id="f7792-108">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="f7792-108">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="f7792-109">関数はトランスポート マネージャーにメモリを割り当てられませんでした。</span><span class="sxs-lookup"><span data-stu-id="f7792-109">The function was unable to allocate memory for a transport manager.</span></span>  
  
 <span data-ttu-id="f7792-110">E_FAIL (またはその他の E_ リターン コード)</span><span class="sxs-lookup"><span data-stu-id="f7792-110">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="f7792-111">その他のエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="f7792-111">Other failures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7792-112">［要件］</span><span class="sxs-lookup"><span data-stu-id="f7792-112">Requirements</span></span>  
 <span data-ttu-id="f7792-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7792-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7792-114">**ヘッダー:** Coreclrremoteデバッグインターフェイス .h</span><span class="sxs-lookup"><span data-stu-id="f7792-114">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="f7792-115">**ライブラリ:** mscordbi_macx86</span><span class="sxs-lookup"><span data-stu-id="f7792-115">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="f7792-116">**.NET Framework のバージョン:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="f7792-116">**.NET Framework Versions:** 3.5 SP1</span></span>
