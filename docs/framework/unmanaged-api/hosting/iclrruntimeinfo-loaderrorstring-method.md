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
ms.openlocfilehash: dd7bdcf891146a15953b7466e0f6dc680495bd5a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64585061"
---
# <a name="iclrruntimeinfoloaderrorstring-method"></a><span data-ttu-id="45b50-102">ICLRRuntimeInfo::LoadErrorString メソッド</span><span class="sxs-lookup"><span data-stu-id="45b50-102">ICLRRuntimeInfo::LoadErrorString Method</span></span>
<span data-ttu-id="45b50-103">HRESULT 値を指定したカルチャの適切なエラー メッセージに変換します。</span><span class="sxs-lookup"><span data-stu-id="45b50-103">Translates an HRESULT value into an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="45b50-104">このメソッドは、次の関数よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="45b50-104">This method supersedes the following functions:</span></span>  
  
- [<span data-ttu-id="45b50-105">LoadStringRC</span><span class="sxs-lookup"><span data-stu-id="45b50-105">LoadStringRC</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)  
  
- [<span data-ttu-id="45b50-106">LoadStringRCEx</span><span class="sxs-lookup"><span data-stu-id="45b50-106">LoadStringRCEx</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)  
  
## <a name="syntax"></a><span data-ttu-id="45b50-107">構文</span><span class="sxs-lookup"><span data-stu-id="45b50-107">Syntax</span></span>  
  
```  
HRESULT LoadErrorString(  
     [in] UINT iResourceID,  
     [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
     [in, out]  DWORD *pcchBuffer,  
     [in, lcid] LONG iLocaleID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="45b50-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="45b50-108">Parameters</span></span>  
 `iResourceID`  
 <span data-ttu-id="45b50-109">[in]変換する HRESULT。</span><span class="sxs-lookup"><span data-stu-id="45b50-109">[in] The HRESULT to translate.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="45b50-110">[out]指定された HRESULT に関連付けられているメッセージ文字列。</span><span class="sxs-lookup"><span data-stu-id="45b50-110">[out] The message string associated with the given HRESULT.</span></span>  
  
 `pcchBuffer`  
 <span data-ttu-id="45b50-111">[入力、出力]サイズ`pwzbuffer`バッファー オーバーランを回避します。</span><span class="sxs-lookup"><span data-stu-id="45b50-111">[in, out] The size of `pwzbuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="45b50-112">場合`pwzbuffer`が null、`pcchBuffer`の予想サイズを提供します。`pwzbuffer`事前割り当てを許可します。</span><span class="sxs-lookup"><span data-stu-id="45b50-112">If `pwzbuffer` is null, `pcchBuffer` provides the expected size of `pwzbuffer` to allow preallocation.</span></span>  
  
 `iLocaleID`  
 <span data-ttu-id="45b50-113">[in]カルチャ識別子。</span><span class="sxs-lookup"><span data-stu-id="45b50-113">[in] The culture identifier.</span></span> <span data-ttu-id="45b50-114">既定のカルチャを使用するには、-1 を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45b50-114">To use the default culture, you must specify -1.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="45b50-115">戻り値</span><span class="sxs-lookup"><span data-stu-id="45b50-115">Return Value</span></span>  
 <span data-ttu-id="45b50-116">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="45b50-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="45b50-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="45b50-117">HRESULT</span></span>|<span data-ttu-id="45b50-118">説明</span><span class="sxs-lookup"><span data-stu-id="45b50-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="45b50-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="45b50-119">S_OK</span></span>|<span data-ttu-id="45b50-120">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="45b50-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="45b50-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="45b50-121">E_POINTER</span></span>|<span data-ttu-id="45b50-122">`pcchBuffer` が null です。</span><span class="sxs-lookup"><span data-stu-id="45b50-122">`pcchBuffer` is null.</span></span>|  
|<span data-ttu-id="45b50-123">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="45b50-123">E_INVALIDARG</span></span>|<span data-ttu-id="45b50-124">`pwzBuffer` が null です。</span><span class="sxs-lookup"><span data-stu-id="45b50-124">`pwzBuffer` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="45b50-125">必要条件</span><span class="sxs-lookup"><span data-stu-id="45b50-125">Requirements</span></span>  
 <span data-ttu-id="45b50-126">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="45b50-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45b50-127">**ヘッダー:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="45b50-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="45b50-128">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="45b50-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="45b50-129">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45b50-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45b50-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="45b50-130">See also</span></span>

- [<span data-ttu-id="45b50-131">ICLRRuntimeInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="45b50-131">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="45b50-132">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="45b50-132">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="45b50-133">ホスティング</span><span class="sxs-lookup"><span data-stu-id="45b50-133">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
