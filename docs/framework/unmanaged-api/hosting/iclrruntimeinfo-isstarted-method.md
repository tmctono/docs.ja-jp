---
title: ICLRRuntimeInfo::IsStarted メソッド
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.IsStarted
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsStarted
helpviewer_keywords:
- IsStarted method [.NET Framework hosting]
- ICLRRuntimeInfo::IsStarted method [.NET Framework hosting]
ms.assetid: ef6f2662-323b-4534-aa82-6d1afb7b9309
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 432de909e1b8166f6d8923889382d9408fb6c62d
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490262"
---
# <a name="iclrruntimeinfoisstarted-method"></a><span data-ttu-id="c7eef-102">ICLRRuntimeInfo::IsStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="c7eef-102">ICLRRuntimeInfo::IsStarted Method</span></span>
<span data-ttu-id="c7eef-103">ランタイムが開始されているかどうかを示します (つまり、かどうか、 [iclrruntimehost::start メソッド](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)が呼び出され、成功しました)。</span><span class="sxs-lookup"><span data-stu-id="c7eef-103">Indicates whether the runtime has been started (that is, whether the [ICLRRuntimeHost::Start method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) has been called and has succeeded).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7eef-104">構文</span><span class="sxs-lookup"><span data-stu-id="c7eef-104">Syntax</span></span>  
  
```  
HRESULT IsStarted(  
        [out] BOOL     *pbStarted,  
        [out] DWORD    *pdwStartupFlags);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7eef-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c7eef-105">Parameters</span></span>  
 `pbStarted`  
 <span data-ttu-id="c7eef-106">[out]`true`このランタイムが開始しました。 それ以外の場合`false`します。</span><span class="sxs-lookup"><span data-stu-id="c7eef-106">[out] `true` if this runtime is started; otherwise, `false`.</span></span>  
  
 `pdwStartupFlags`  
 <span data-ttu-id="c7eef-107">[out]ランタイムを開始するために使用されたフラグを返します。</span><span class="sxs-lookup"><span data-stu-id="c7eef-107">[out] Returns the flags that were used to start the runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c7eef-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="c7eef-108">Return Value</span></span>  
 <span data-ttu-id="c7eef-109">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="c7eef-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="c7eef-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c7eef-110">HRESULT</span></span>|<span data-ttu-id="c7eef-111">説明</span><span class="sxs-lookup"><span data-stu-id="c7eef-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c7eef-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="c7eef-112">S_OK</span></span>|<span data-ttu-id="c7eef-113">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="c7eef-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="c7eef-114">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="c7eef-114">E_NOTIMPL</span></span>|<span data-ttu-id="c7eef-115">共通言語ランタイム (CLR) バージョンは、.NET Framework 4 で CLR のバージョンより前です。</span><span class="sxs-lookup"><span data-stu-id="c7eef-115">The common language runtime (CLR) version is earlier than the CLR version in the .NET Framework 4.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c7eef-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="c7eef-116">Remarks</span></span>  
 <span data-ttu-id="c7eef-117">このメソッドは使えません CLR のバージョンと .NET Framework 4 で CLR のバージョンよりも前。</span><span class="sxs-lookup"><span data-stu-id="c7eef-117">This method does not work with CLR versions earlier than the CLR version in the .NET Framework 4.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7eef-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="c7eef-118">Requirements</span></span>  
 <span data-ttu-id="c7eef-119">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7eef-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7eef-120">**ヘッダー:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="c7eef-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="c7eef-121">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="c7eef-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c7eef-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7eef-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7eef-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="c7eef-123">See also</span></span>

- [<span data-ttu-id="c7eef-124">ICLRRuntimeInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c7eef-124">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="c7eef-125">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c7eef-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="c7eef-126">ホスティング</span><span class="sxs-lookup"><span data-stu-id="c7eef-126">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
