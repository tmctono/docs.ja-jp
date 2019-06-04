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
ms.openlocfilehash: f938c7dcf08654eef1e2403426eb5c54d6d2a6b3
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490125"
---
# <a name="waitortimercallback-function-pointer"></a><span data-ttu-id="50c29-102">WAITORTIMERCALLBACK 関数ポインター</span><span class="sxs-lookup"><span data-stu-id="50c29-102">WAITORTIMERCALLBACK Function Pointer</span></span>
<span data-ttu-id="50c29-103">待機を処理するホストに通知する関数を指します (<xref:System.Threading.WaitHandle>) がされたシグナルまたはタイムアウトします。</span><span class="sxs-lookup"><span data-stu-id="50c29-103">Points to a function that notifies the host that a wait handle (<xref:System.Threading.WaitHandle>) has either been signaled or timed out.</span></span>  
  
 <span data-ttu-id="50c29-104">この関数ポインターは、.NET Framework 4 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="50c29-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50c29-105">構文</span><span class="sxs-lookup"><span data-stu-id="50c29-105">Syntax</span></span>  
  
```  
typedef VOID (__stdcall *WAITORTIMERCALLBACK) (  
    [in] PVOID lpParameter,  
    [in] BOOL  TimerOrWaitFired  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="50c29-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="50c29-106">Parameters</span></span>  
 `lpParameter`  
 <span data-ttu-id="50c29-107">[in]ホストによって定義された情報を格納しているオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="50c29-107">[in] A pointer to an object that contains information defined by the host.</span></span>  
  
 `TimerOrWaitFired`  
 <span data-ttu-id="50c29-108">[in]`true`待機ハンドルがタイムアウトした場合または`false`シグナル通知された場合。</span><span class="sxs-lookup"><span data-stu-id="50c29-108">[in] `true` if the wait handle timed out, or `false` if it was signaled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="50c29-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="50c29-109">Remarks</span></span>  
 <span data-ttu-id="50c29-110">関数`WAITORTIMERCALLBACK`ポイントはコールバック関数であり、ホスト アプリケーションの作成者によって実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="50c29-110">The function to which `WAITORTIMERCALLBACK` points is a callback function and must be implemented by the writer of the hosting application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50c29-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="50c29-111">Requirements</span></span>  
 <span data-ttu-id="50c29-112">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="50c29-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50c29-113">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="50c29-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="50c29-114">**ライブラリ:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="50c29-114">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="50c29-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50c29-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50c29-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="50c29-116">See also</span></span>

- [<span data-ttu-id="50c29-117">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="50c29-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
