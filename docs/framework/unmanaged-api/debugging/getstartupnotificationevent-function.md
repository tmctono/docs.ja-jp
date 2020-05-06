---
title: GetStartupNotificationEvent 関数
ms.date: 03/30/2017
api_name:
- GetStartupNotificationEvent
api_location:
- dbgshim.dll
api_type:
- COM
f1_keywords:
- GetStartupNotificationEvent
helpviewer_keywords:
- GetStartupNotificationEvent function
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: c94b1b61-045a-4695-bacd-0f18c5acc246
topic_type:
- apiref
ms.openlocfilehash: 3377dcd5d45ca8e31a57a75bd81366d41837c12c
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860717"
---
# <a name="getstartupnotificationevent-function"></a><span data-ttu-id="4c5fc-102">GetStartupNotificationEvent 関数</span><span class="sxs-lookup"><span data-stu-id="4c5fc-102">GetStartupNotificationEvent Function</span></span>
<span data-ttu-id="4c5fc-103">指定された対象プロセスに読み込まれている任意の共通言語ランタイム (CLR: Common Language Runtime) によって通知されるイベント ハンドルを作成または開きます。</span><span class="sxs-lookup"><span data-stu-id="4c5fc-103">Creates or opens an event handle that will be signaled upon by any common language runtime (CLR) that is loading in the specified target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c5fc-104">構文</span><span class="sxs-lookup"><span data-stu-id="4c5fc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStartupNotificationEvent  
    (  
    [in]  DWORD     debuggeePID,  
    [out]  HANDLE*  phStartupEvent  
    );  
```  
  
## <a name="parameters"></a><span data-ttu-id="4c5fc-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4c5fc-105">Parameters</span></span>  
 `debuggeePID`  
 <span data-ttu-id="4c5fc-106">[in] 受信する CLR スタートアップ通知の送信元である対象プロセスのプロセス識別子。</span><span class="sxs-lookup"><span data-stu-id="4c5fc-106">[in] Process identifier of the target process from which to receive CLR startup notifications.</span></span>  
  
 `phStartupEvent`  
 <span data-ttu-id="4c5fc-107">[out] スタートアップ時に CLR によって通知されるハンドルへのポインター。</span><span class="sxs-lookup"><span data-stu-id="4c5fc-107">[out] A pointer to a handle that will be signaled by a CLR on startup.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4c5fc-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="4c5fc-108">Return Value</span></span>  
 <span data-ttu-id="4c5fc-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="4c5fc-109">S_OK</span></span>  
 <span data-ttu-id="4c5fc-110">スタートアップ通知イベントに対するハンドルを正常に取得しました。</span><span class="sxs-lookup"><span data-stu-id="4c5fc-110">Successfully obtained the handle to the startup notification event.</span></span>  
  
 <span data-ttu-id="4c5fc-111">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="4c5fc-111">E_INVALIDARG</span></span>  
 <span data-ttu-id="4c5fc-112">`phStartupEvent` が nullであるか、または `debuggeePID` が現在実行されているプロセスを参照していません。</span><span class="sxs-lookup"><span data-stu-id="4c5fc-112">`phStartupEvent` is null or `debuggeePID` does not refer to a process that is currently running.</span></span>  
  
 <span data-ttu-id="4c5fc-113">E_FAIL (またはその他の E_ リターン コード)</span><span class="sxs-lookup"><span data-stu-id="4c5fc-113">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="4c5fc-114">スタートアップ通知イベントに対するハンドルを取得できません。</span><span class="sxs-lookup"><span data-stu-id="4c5fc-114">Unable to obtain the handle to the startup notification event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4c5fc-115">解説</span><span class="sxs-lookup"><span data-stu-id="4c5fc-115">Remarks</span></span>  
 <span data-ttu-id="4c5fc-116">Windows オペレーティング システムでは、`debuggeePID` がプロセス識別子に対応づけられます。</span><span class="sxs-lookup"><span data-stu-id="4c5fc-116">On the Windows operating system, `debuggeePID` maps to an OS process identifier.</span></span>  
  
 <span data-ttu-id="4c5fc-117">イベントは、通知元の CLR によってマネージド コードが実行される前に通知されます。</span><span class="sxs-lookup"><span data-stu-id="4c5fc-117">The event is signaled before any managed code is executed by the CLR that signaled the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c5fc-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="4c5fc-118">Requirements</span></span>  
 <span data-ttu-id="4c5fc-119">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c5fc-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c5fc-120">**ヘッダー:** dbgshim. h</span><span class="sxs-lookup"><span data-stu-id="4c5fc-120">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="4c5fc-121">**ライブラリ:** dbgshim .dll</span><span class="sxs-lookup"><span data-stu-id="4c5fc-121">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="4c5fc-122">**.NET Framework のバージョン:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="4c5fc-122">**.NET Framework Versions:** 3.5 SP1</span></span>
