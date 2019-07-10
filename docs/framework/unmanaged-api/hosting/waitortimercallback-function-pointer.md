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
ms.openlocfilehash: 65af5303468904ee40da4d567381782af70bfb38
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776502"
---
# <a name="waitortimercallback-function-pointer"></a><span data-ttu-id="9ad0b-102">WAITORTIMERCALLBACK 関数ポインター</span><span class="sxs-lookup"><span data-stu-id="9ad0b-102">WAITORTIMERCALLBACK Function Pointer</span></span>
<span data-ttu-id="9ad0b-103">待機を処理するホストに通知する関数を指します (<xref:System.Threading.WaitHandle>) がされたシグナルまたはタイムアウトします。</span><span class="sxs-lookup"><span data-stu-id="9ad0b-103">Points to a function that notifies the host that a wait handle (<xref:System.Threading.WaitHandle>) has either been signaled or timed out.</span></span>  
  
 <span data-ttu-id="9ad0b-104">この関数ポインターは、.NET Framework 4 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="9ad0b-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ad0b-105">構文</span><span class="sxs-lookup"><span data-stu-id="9ad0b-105">Syntax</span></span>  
  
```cpp  
typedef VOID (__stdcall *WAITORTIMERCALLBACK) (  
    [in] PVOID lpParameter,  
    [in] BOOL  TimerOrWaitFired  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9ad0b-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9ad0b-106">Parameters</span></span>  
 `lpParameter`  
 <span data-ttu-id="9ad0b-107">[in]ホストによって定義された情報を格納しているオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="9ad0b-107">[in] A pointer to an object that contains information defined by the host.</span></span>  
  
 `TimerOrWaitFired`  
 <span data-ttu-id="9ad0b-108">[in]`true`待機ハンドルがタイムアウトした場合または`false`シグナル通知された場合。</span><span class="sxs-lookup"><span data-stu-id="9ad0b-108">[in] `true` if the wait handle timed out, or `false` if it was signaled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9ad0b-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="9ad0b-109">Remarks</span></span>  
 <span data-ttu-id="9ad0b-110">関数`WAITORTIMERCALLBACK`ポイントはコールバック関数であり、ホスト アプリケーションの作成者によって実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ad0b-110">The function to which `WAITORTIMERCALLBACK` points is a callback function and must be implemented by the writer of the hosting application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ad0b-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="9ad0b-111">Requirements</span></span>  
 <span data-ttu-id="9ad0b-112">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ad0b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ad0b-113">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9ad0b-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9ad0b-114">**ライブラリ:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="9ad0b-114">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="9ad0b-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ad0b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ad0b-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="9ad0b-116">See also</span></span>

- [<span data-ttu-id="9ad0b-117">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="9ad0b-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
