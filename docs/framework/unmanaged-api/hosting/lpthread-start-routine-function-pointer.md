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
ms.openlocfilehash: 577526536e07172070a1e8a65e73fd15646681fb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67768350"
---
# <a name="lpthreadstartroutine-function-pointer"></a><span data-ttu-id="a3087-102">LPTHREAD_START_ROUTINE 関数ポインター</span><span class="sxs-lookup"><span data-stu-id="a3087-102">LPTHREAD_START_ROUTINE Function Pointer</span></span>
<span data-ttu-id="a3087-103">スレッドの実行を開始したことをホストに通知する関数を指します。</span><span class="sxs-lookup"><span data-stu-id="a3087-103">Points to a function that notifies the host that a thread has started to execute.</span></span>  
  
 <span data-ttu-id="a3087-104">この関数ポインターは、.NET Framework 4 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="a3087-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3087-105">構文</span><span class="sxs-lookup"><span data-stu-id="a3087-105">Syntax</span></span>  
  
```cpp  
typedef DWORD (__stdcall *LPTHREAD_START_ROUTINE) (  
    [in] LPVOID lpThreadParameter  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3087-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a3087-106">Parameters</span></span>  
 `lpThreadParameter`  
 <span data-ttu-id="a3087-107">[in]実行を開始するコードへのポインター。</span><span class="sxs-lookup"><span data-stu-id="a3087-107">[in] A pointer to the code that has started executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a3087-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="a3087-108">Remarks</span></span>  
 <span data-ttu-id="a3087-109">関数`LPTHREAD_START_ROUTINE`ポイントはコールバック関数であり、ホスト アプリケーションの作成者によって実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3087-109">The function to which `LPTHREAD_START_ROUTINE` points is a callback function and must be implemented by the writer of the hosting application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3087-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="a3087-110">Requirements</span></span>  
 <span data-ttu-id="a3087-111">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3087-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3087-112">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a3087-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a3087-113">**ライブラリ:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="a3087-113">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="a3087-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3087-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3087-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="a3087-115">See also</span></span>

- [<span data-ttu-id="a3087-116">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="a3087-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
