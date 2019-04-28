---
title: ICLRRuntimeInfo::IsLoadable メソッド
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.IsLoadable
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsLoadable
helpviewer_keywords:
- IsLoadable method [.NET Framework hosting]
- ICLRRuntimeInfo::IsLoadable method [.NET Framework hosting]
ms.assetid: 205ca53b-e78e-49b2-9a46-2a7823e96b8c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 52257b30b8172b80f968df25115956b6995c1552
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771736"
---
# <a name="iclrruntimeinfoisloadable-method"></a><span data-ttu-id="71734-102">ICLRRuntimeInfo::IsLoadable メソッド</span><span class="sxs-lookup"><span data-stu-id="71734-102">ICLRRuntimeInfo::IsLoadable Method</span></span>
<span data-ttu-id="71734-103">このインターフェイスに関連付けられているランタイムを考慮して、現在のプロセスに読み込めるかどうかを示す、プロセスに読み込まれることが既にある他のランタイム。</span><span class="sxs-lookup"><span data-stu-id="71734-103">Indicates whether the runtime associated with this interface can be loaded into the current process, taking into account other runtimes that might already be loaded into the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71734-104">構文</span><span class="sxs-lookup"><span data-stu-id="71734-104">Syntax</span></span>  
  
```  
HRESULT IsLoadable(  
        [out, retval] BOOL *pbLoadable);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71734-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="71734-105">Parameters</span></span>  
 `pbLoadable`  
 <span data-ttu-id="71734-106">[out]`true`このランタイムは、現在のプロセスに読み込まれます。 それ以外にできる場合は`false`します。</span><span class="sxs-lookup"><span data-stu-id="71734-106">[out] `true` if this runtime could be loaded into the current process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="71734-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="71734-107">Return Value</span></span>  
 <span data-ttu-id="71734-108">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="71734-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="71734-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="71734-109">HRESULT</span></span>|<span data-ttu-id="71734-110">説明</span><span class="sxs-lookup"><span data-stu-id="71734-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="71734-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="71734-111">S_OK</span></span>|<span data-ttu-id="71734-112">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="71734-112">The method completed successfully.</span></span>|  
|<span data-ttu-id="71734-113">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="71734-113">E_POINTER</span></span>|<span data-ttu-id="71734-114">`pbLoadable` が null です。</span><span class="sxs-lookup"><span data-stu-id="71734-114">`pbLoadable` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71734-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="71734-115">Remarks</span></span>  
 <span data-ttu-id="71734-116">別のランタイムが既にプロセスに読み込まれていて、インプロセスでサイド バイ サイドで実行するため、このインターフェイスに関連付けられているランタイムを読み込める`pbLoadable`返します`true`します。</span><span class="sxs-lookup"><span data-stu-id="71734-116">If another runtime is already loaded into the process and the runtime associated with this interface can be loaded for in-process side-by-side execution, `pbLoadable` returns `true`.</span></span> <span data-ttu-id="71734-117">2 つのランタイムはサイド バイ サイドでインプロセスで実行できない場合`pbLoadable`返します`false`します。</span><span class="sxs-lookup"><span data-stu-id="71734-117">If the two runtimes cannot run side-by-side in-process, `pbLoadable` returns `false`.</span></span> <span data-ttu-id="71734-118">たとえば、共通言語ランタイム (CLR) バージョン 4 では、CLR バージョン 2.0 を使用して同じプロセス内で並列してまたは CLR バージョン 1.1 を実行できます。</span><span class="sxs-lookup"><span data-stu-id="71734-118">For example, the common language runtime (CLR) version 4 can run side-by-side in the same process with CLR version 2.0 or CLR version 1.1.</span></span> <span data-ttu-id="71734-119">ただし、CLR の version 1.1 と CLR の version 2.0 では、サイド バイ サイドでプロセスを実行できません。</span><span class="sxs-lookup"><span data-stu-id="71734-119">However, CLR version 1.1 and CLR version 2.0 cannot run side-by-side in-process.</span></span>  
  
 <span data-ttu-id="71734-120">かどうかは、プロセスにランタイムが読み込まれません、このメソッドはその常に返します`true`します。</span><span class="sxs-lookup"><span data-stu-id="71734-120">If no runtimes are loaded into the process, this method always returns `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71734-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="71734-121">Requirements</span></span>  
 <span data-ttu-id="71734-122">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="71734-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71734-123">**ヘッダー:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="71734-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="71734-124">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="71734-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="71734-125">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71734-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71734-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="71734-126">See also</span></span>

- [<span data-ttu-id="71734-127">ICLRRuntimeInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="71734-127">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="71734-128">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="71734-128">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="71734-129">ホスティング</span><span class="sxs-lookup"><span data-stu-id="71734-129">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
