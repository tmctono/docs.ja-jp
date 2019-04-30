---
title: WAITORTIMERCALLBACK 関数ポインター
ms.date: 03/30/2017
api_name:
- WAITORTIMERCALLBACK
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- WAITORTIMERCALLBACK
helpviewer_keywords:
- WAITORTIMERCALLBACK function pointer [.NET Framework hosting]
ms.assetid: 1fec4aef-0a06-4df0-bae7-d31a9ef9603d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f8cf12fc6828c5e439a6a86532f22b8a598a9f03
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62043327"
---
# <a name="waitortimercallback-function-pointer"></a><span data-ttu-id="a4df3-102">WAITORTIMERCALLBACK 関数ポインター</span><span class="sxs-lookup"><span data-stu-id="a4df3-102">WAITORTIMERCALLBACK Function Pointer</span></span>
<span data-ttu-id="a4df3-103">待機を処理するホストに通知する関数を指します (<xref:System.Threading.WaitHandle>) がされたシグナルまたはタイムアウトします。</span><span class="sxs-lookup"><span data-stu-id="a4df3-103">Points to a function that notifies the host that a wait handle (<xref:System.Threading.WaitHandle>) has either been signaled or timed out.</span></span>  
  
 <span data-ttu-id="a4df3-104">この関数のポインターが非推奨とされた、[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="a4df3-104">This function pointer has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4df3-105">構文</span><span class="sxs-lookup"><span data-stu-id="a4df3-105">Syntax</span></span>  
  
```  
typedef VOID (__stdcall *WAITORTIMERCALLBACK) (  
    [in] PVOID lpParameter,  
    [in] BOOL  TimerOrWaitFired  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a4df3-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a4df3-106">Parameters</span></span>  
 `lpParameter`  
 <span data-ttu-id="a4df3-107">[in]ホストによって定義された情報を格納しているオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="a4df3-107">[in] A pointer to an object that contains information defined by the host.</span></span>  
  
 `TimerOrWaitFired`  
 <span data-ttu-id="a4df3-108">[in]`true`待機ハンドルがタイムアウトした場合または`false`シグナル通知された場合。</span><span class="sxs-lookup"><span data-stu-id="a4df3-108">[in] `true` if the wait handle timed out, or `false` if it was signaled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a4df3-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="a4df3-109">Remarks</span></span>  
 <span data-ttu-id="a4df3-110">関数`WAITORTIMERCALLBACK`ポイントはコールバック関数であり、ホスト アプリケーションの作成者によって実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4df3-110">The function to which `WAITORTIMERCALLBACK` points is a callback function and must be implemented by the writer of the hosting application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4df3-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="a4df3-111">Requirements</span></span>  
 <span data-ttu-id="a4df3-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4df3-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4df3-113">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a4df3-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a4df3-114">**ライブラリ:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="a4df3-114">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="a4df3-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4df3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4df3-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="a4df3-116">See also</span></span>

- [<span data-ttu-id="a4df3-117">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="a4df3-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
