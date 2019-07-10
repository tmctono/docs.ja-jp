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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 948e97064d12dc5b2044faf35aa374e5ba5f2592
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764782"
---
# <a name="initdbgtransportmanager-function"></a><span data-ttu-id="72c35-102">InitDbgTransportManager 関数</span><span class="sxs-lookup"><span data-stu-id="72c35-102">InitDbgTransportManager Function</span></span>
<span data-ttu-id="72c35-103">プロセスおよびランタイムの列挙のためにリモート ターゲットに接続するよう、トランスポート マネージャーを初期化します。</span><span class="sxs-lookup"><span data-stu-id="72c35-103">Initializes the transport manager to connect to a remote target for process and runtime enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72c35-104">構文</span><span class="sxs-lookup"><span data-stu-id="72c35-104">Syntax</span></span>  
  
```cpp  
HRESULT InitDbgTransportManager ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="72c35-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="72c35-105">Return Value</span></span>  
 <span data-ttu-id="72c35-106">S_OK</span><span class="sxs-lookup"><span data-stu-id="72c35-106">S_OK</span></span>  
 <span data-ttu-id="72c35-107">成功。</span><span class="sxs-lookup"><span data-stu-id="72c35-107">Success.</span></span>  
  
 <span data-ttu-id="72c35-108">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="72c35-108">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="72c35-109">関数はトランスポート マネージャーにメモリを割り当てられませんでした。</span><span class="sxs-lookup"><span data-stu-id="72c35-109">The function was unable to allocate memory for a transport manager.</span></span>  
  
 <span data-ttu-id="72c35-110">E_FAIL (またはその他の E_ リターン コード)</span><span class="sxs-lookup"><span data-stu-id="72c35-110">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="72c35-111">その他のエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="72c35-111">Other failures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72c35-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="72c35-112">Requirements</span></span>  
 <span data-ttu-id="72c35-113">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="72c35-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72c35-114">**ヘッダー:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="72c35-114">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="72c35-115">**ライブラリ:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="72c35-115">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="72c35-116">**.NET framework のバージョン:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="72c35-116">**.NET Framework Versions:** 3.5 SP1</span></span>
