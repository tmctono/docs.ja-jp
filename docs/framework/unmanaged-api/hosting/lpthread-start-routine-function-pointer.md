---
title: LPTHREAD_START_ROUTINE 関数ポインター
ms.date: 03/30/2017
api_name:
- LPTHREAD_START_ROUTINE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- LPTHREAD_START_ROUTINE
helpviewer_keywords:
- LPTHREAD_START_ROUTINE function pointer [.NET Framework hosting]
ms.assetid: 7b9b93b0-fe92-42ba-8693-701168a29dde
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a81e78c0a34f766e1598dd27506f62bd3132f348
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490162"
---
# <a name="lpthreadstartroutine-function-pointer"></a><span data-ttu-id="85d08-102">LPTHREAD_START_ROUTINE 関数ポインター</span><span class="sxs-lookup"><span data-stu-id="85d08-102">LPTHREAD_START_ROUTINE Function Pointer</span></span>
<span data-ttu-id="85d08-103">スレッドの実行を開始したことをホストに通知する関数を指します。</span><span class="sxs-lookup"><span data-stu-id="85d08-103">Points to a function that notifies the host that a thread has started to execute.</span></span>  
  
 <span data-ttu-id="85d08-104">この関数ポインターは、.NET Framework 4 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="85d08-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85d08-105">構文</span><span class="sxs-lookup"><span data-stu-id="85d08-105">Syntax</span></span>  
  
```  
typedef DWORD (__stdcall *LPTHREAD_START_ROUTINE) (  
    [in] LPVOID lpThreadParameter  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="85d08-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="85d08-106">Parameters</span></span>  
 `lpThreadParameter`  
 <span data-ttu-id="85d08-107">[in]実行を開始するコードへのポインター。</span><span class="sxs-lookup"><span data-stu-id="85d08-107">[in] A pointer to the code that has started executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="85d08-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="85d08-108">Remarks</span></span>  
 <span data-ttu-id="85d08-109">関数`LPTHREAD_START_ROUTINE`ポイントはコールバック関数であり、ホスト アプリケーションの作成者によって実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="85d08-109">The function to which `LPTHREAD_START_ROUTINE` points is a callback function and must be implemented by the writer of the hosting application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85d08-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="85d08-110">Requirements</span></span>  
 <span data-ttu-id="85d08-111">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="85d08-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85d08-112">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="85d08-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="85d08-113">**ライブラリ:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="85d08-113">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="85d08-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85d08-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85d08-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="85d08-115">See also</span></span>

- [<span data-ttu-id="85d08-116">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="85d08-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
