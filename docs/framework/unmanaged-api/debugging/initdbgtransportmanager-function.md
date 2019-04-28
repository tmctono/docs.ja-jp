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
ms.openlocfilehash: 74cb2c7d1f79d23e1331cc7192ba2d6acfd9835c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61761651"
---
# <a name="initdbgtransportmanager-function"></a><span data-ttu-id="de028-102">InitDbgTransportManager 関数</span><span class="sxs-lookup"><span data-stu-id="de028-102">InitDbgTransportManager Function</span></span>
<span data-ttu-id="de028-103">プロセスおよびランタイムの列挙のためにリモート ターゲットに接続するよう、トランスポート マネージャーを初期化します。</span><span class="sxs-lookup"><span data-stu-id="de028-103">Initializes the transport manager to connect to a remote target for process and runtime enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de028-104">構文</span><span class="sxs-lookup"><span data-stu-id="de028-104">Syntax</span></span>  
  
```  
HRESULT InitDbgTransportManager ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="de028-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="de028-105">Return Value</span></span>  
 <span data-ttu-id="de028-106">S_OK</span><span class="sxs-lookup"><span data-stu-id="de028-106">S_OK</span></span>  
 <span data-ttu-id="de028-107">成功。</span><span class="sxs-lookup"><span data-stu-id="de028-107">Success.</span></span>  
  
 <span data-ttu-id="de028-108">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="de028-108">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="de028-109">関数はトランスポート マネージャーにメモリを割り当てられませんでした。</span><span class="sxs-lookup"><span data-stu-id="de028-109">The function was unable to allocate memory for a transport manager.</span></span>  
  
 <span data-ttu-id="de028-110">E_FAIL (またはその他の E_ リターン コード)</span><span class="sxs-lookup"><span data-stu-id="de028-110">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="de028-111">その他のエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="de028-111">Other failures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de028-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="de028-112">Requirements</span></span>  
 <span data-ttu-id="de028-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="de028-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de028-114">**ヘッダー:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="de028-114">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="de028-115">**ライブラリ:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="de028-115">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="de028-116">**.NET framework のバージョン:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="de028-116">**.NET Framework Versions:** 3.5 SP1</span></span>
