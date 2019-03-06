---
title: ICLRRuntimeInfo::LoadErrorString メソッド
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.LoadErrorString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::LoadErrorString
helpviewer_keywords:
- ICLRRuntimeInfo::LoadErrorString method [.NET Framework hosting]
- LoadErrorString method [.NET Framework hosting]
ms.assetid: 52c543ab-9ef5-4ee7-b836-c0ffc35cd45b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a565c19285b00c807ef6fbfc018a40467139638e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466350"
---
# <a name="iclrruntimeinfoloaderrorstring-method"></a><span data-ttu-id="db0f2-102">ICLRRuntimeInfo::LoadErrorString メソッド</span><span class="sxs-lookup"><span data-stu-id="db0f2-102">ICLRRuntimeInfo::LoadErrorString Method</span></span>
<span data-ttu-id="db0f2-103">HRESULT 値を指定したカルチャの適切なエラー メッセージに変換します。</span><span class="sxs-lookup"><span data-stu-id="db0f2-103">Translates an HRESULT value into an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="db0f2-104">このメソッドは、次の関数よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="db0f2-104">This method supersedes the following functions:</span></span>  
  
-   [<span data-ttu-id="db0f2-105">LoadStringRC</span><span class="sxs-lookup"><span data-stu-id="db0f2-105">LoadStringRC</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)  
  
-   [<span data-ttu-id="db0f2-106">LoadStringRCEx</span><span class="sxs-lookup"><span data-stu-id="db0f2-106">LoadStringRCEx</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)  
  
## <a name="syntax"></a><span data-ttu-id="db0f2-107">構文</span><span class="sxs-lookup"><span data-stu-id="db0f2-107">Syntax</span></span>  
  
```  
HRESULT LoadErrorString(  
     [in] UINT iResourceID,  
     [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
     [in, out]  DWORD *pcchBuffer,  
     [in, lcid] LONG iLocaleID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="db0f2-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="db0f2-108">Parameters</span></span>  
 `iResourceID`  
 <span data-ttu-id="db0f2-109">[in]変換する HRESULT。</span><span class="sxs-lookup"><span data-stu-id="db0f2-109">[in] The HRESULT to translate.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="db0f2-110">[out]指定された HRESULT に関連付けられているメッセージ文字列。</span><span class="sxs-lookup"><span data-stu-id="db0f2-110">[out] The message string associated with the given HRESULT.</span></span>  
  
 `pcchBuffer`  
 <span data-ttu-id="db0f2-111">[入力、出力]サイズ`pwzbuffer`バッファー オーバーランを回避します。</span><span class="sxs-lookup"><span data-stu-id="db0f2-111">[in, out] The size of `pwzbuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="db0f2-112">場合`pwzbuffer`が null、`pcchBuffer`の予想サイズを提供します。`pwzbuffer`事前割り当てを許可します。</span><span class="sxs-lookup"><span data-stu-id="db0f2-112">If `pwzbuffer` is null, `pcchBuffer` provides the expected size of `pwzbuffer` to allow preallocation.</span></span>  
  
 `iLocaleID`  
 <span data-ttu-id="db0f2-113">[in]カルチャ識別子。</span><span class="sxs-lookup"><span data-stu-id="db0f2-113">[in] The culture identifier.</span></span> <span data-ttu-id="db0f2-114">既定のカルチャを使用するには、-1 を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="db0f2-114">To use the default culture, you must specify -1.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="db0f2-115">戻り値</span><span class="sxs-lookup"><span data-stu-id="db0f2-115">Return Value</span></span>  
 <span data-ttu-id="db0f2-116">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="db0f2-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="db0f2-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="db0f2-117">HRESULT</span></span>|<span data-ttu-id="db0f2-118">説明</span><span class="sxs-lookup"><span data-stu-id="db0f2-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="db0f2-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="db0f2-119">S_OK</span></span>|<span data-ttu-id="db0f2-120">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="db0f2-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="db0f2-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="db0f2-121">E_POINTER</span></span>|<span data-ttu-id="db0f2-122">`pcchBuffer` が null です。</span><span class="sxs-lookup"><span data-stu-id="db0f2-122">`pcchBuffer` is null.</span></span>|  
|<span data-ttu-id="db0f2-123">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="db0f2-123">E_INVALIDARG</span></span>|<span data-ttu-id="db0f2-124">`pwzBuffer` が null です。</span><span class="sxs-lookup"><span data-stu-id="db0f2-124">`pwzBuffer` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="db0f2-125">必要条件</span><span class="sxs-lookup"><span data-stu-id="db0f2-125">Requirements</span></span>  
 <span data-ttu-id="db0f2-126">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="db0f2-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db0f2-127">**ヘッダー:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="db0f2-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="db0f2-128">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="db0f2-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="db0f2-129">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db0f2-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db0f2-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="db0f2-130">See also</span></span>
- [<span data-ttu-id="db0f2-131">ICLRRuntimeInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="db0f2-131">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="db0f2-132">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="db0f2-132">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="db0f2-133">ホスティング</span><span class="sxs-lookup"><span data-stu-id="db0f2-133">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
