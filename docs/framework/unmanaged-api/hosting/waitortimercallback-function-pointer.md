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
ms.openlocfilehash: ee5dd611888ec52e360ef45fab4c01e9c5b2d6bb
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009451"
---
# <a name="waitortimercallback-function-pointer"></a><span data-ttu-id="f4f9a-102">WAITORTIMERCALLBACK 関数ポインター</span><span class="sxs-lookup"><span data-stu-id="f4f9a-102">WAITORTIMERCALLBACK Function Pointer</span></span>
<span data-ttu-id="f4f9a-103">待機ハンドル () がシグナル状態になったか、タイムアウトしたことをホストに通知する関数を指し <xref:System.Threading.WaitHandle> ます。</span><span class="sxs-lookup"><span data-stu-id="f4f9a-103">Points to a function that notifies the host that a wait handle (<xref:System.Threading.WaitHandle>) has either been signaled or timed out.</span></span>  
  
 <span data-ttu-id="f4f9a-104">この関数ポインターは .NET Framework 4 で非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="f4f9a-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4f9a-105">構文</span><span class="sxs-lookup"><span data-stu-id="f4f9a-105">Syntax</span></span>  
  
```cpp  
typedef VOID (__stdcall *WAITORTIMERCALLBACK) (  
    [in] PVOID lpParameter,  
    [in] BOOL  TimerOrWaitFired  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4f9a-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f4f9a-106">Parameters</span></span>  
 `lpParameter`  
 <span data-ttu-id="f4f9a-107">からホストによって定義された情報を格納しているオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="f4f9a-107">[in] A pointer to an object that contains information defined by the host.</span></span>  
  
 `TimerOrWaitFired`  
 <span data-ttu-id="f4f9a-108">[入力] `true`待機ハンドルがタイムアウトした場合は `false` 。それがシグナル状態だった場合は。</span><span class="sxs-lookup"><span data-stu-id="f4f9a-108">[in] `true` if the wait handle timed out, or `false` if it was signaled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f4f9a-109">コメント</span><span class="sxs-lookup"><span data-stu-id="f4f9a-109">Remarks</span></span>  
 <span data-ttu-id="f4f9a-110">`WAITORTIMERCALLBACK`ポイントがコールバック関数であり、ホストアプリケーションのライターによって実装されている必要がある関数。</span><span class="sxs-lookup"><span data-stu-id="f4f9a-110">The function to which `WAITORTIMERCALLBACK` points is a callback function and must be implemented by the writer of the hosting application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4f9a-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="f4f9a-111">Requirements</span></span>  
 <span data-ttu-id="f4f9a-112">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4f9a-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4f9a-113">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="f4f9a-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f4f9a-114">**ライブラリ:** Mscorwks.dll</span><span class="sxs-lookup"><span data-stu-id="f4f9a-114">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="f4f9a-115">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4f9a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4f9a-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="f4f9a-116">See also</span></span>

- [<span data-ttu-id="f4f9a-117">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="f4f9a-117">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
