---
title: ICLRRuntimeInfo::GetProcAddress メソッド
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetProcAddress
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetProcAddress
helpviewer_keywords:
- GetProcAddress method [.NET Framework hosting]
- ICLRRuntimeInfo::GetProcAddress method [.NET Framework hosting]
ms.assetid: a7732bfc-689a-4926-88fd-4f81e6f9ed78
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c196eafbc2ff1d851471355a630b860c7c02ba1b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67765542"
---
# <a name="iclrruntimeinfogetprocaddress-method"></a><span data-ttu-id="808e8-102">ICLRRuntimeInfo::GetProcAddress メソッド</span><span class="sxs-lookup"><span data-stu-id="808e8-102">ICLRRuntimeInfo::GetProcAddress Method</span></span>
<span data-ttu-id="808e8-103">このインターフェイスに関連付けられている共通言語ランタイム (CLR) からエクスポートされた、指定された関数のアドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="808e8-103">Gets the address of a specified function that was exported from the common language runtime (CLR) associated with this interface.</span></span>  
  
 <span data-ttu-id="808e8-104">このメソッドは、 [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md)関数。</span><span class="sxs-lookup"><span data-stu-id="808e8-104">This method supersedes the [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="808e8-105">構文</span><span class="sxs-lookup"><span data-stu-id="808e8-105">Syntax</span></span>  
  
```cpp  
HRESULT GetProcAddress(  
     [in]  LPCSTR pszProcName,  
     [out, retval] LPVOID *ppProc);  
```  
  
## <a name="parameters"></a><span data-ttu-id="808e8-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="808e8-106">Parameters</span></span>  
 `pszProcName`  
 <span data-ttu-id="808e8-107">[in]エクスポートされた関数の名前。</span><span class="sxs-lookup"><span data-stu-id="808e8-107">[in] The name of the exported function.</span></span>  
  
 `ppProc`  
 <span data-ttu-id="808e8-108">[out]エクスポートされた関数のアドレス。</span><span class="sxs-lookup"><span data-stu-id="808e8-108">[out] The address of the exported function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="808e8-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="808e8-109">Return Value</span></span>  
 <span data-ttu-id="808e8-110">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="808e8-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="808e8-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="808e8-111">HRESULT</span></span>|<span data-ttu-id="808e8-112">説明</span><span class="sxs-lookup"><span data-stu-id="808e8-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="808e8-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="808e8-113">S_OK</span></span>|<span data-ttu-id="808e8-114">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="808e8-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="808e8-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="808e8-115">E_POINTER</span></span>|<span data-ttu-id="808e8-116">`pszProcName` または `ppProc` が null です。</span><span class="sxs-lookup"><span data-stu-id="808e8-116">`pszProcName` or `ppProc` is null.</span></span>|  
|<span data-ttu-id="808e8-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="808e8-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="808e8-118">指定された関数は、エクスポートされた関数ではありません。</span><span class="sxs-lookup"><span data-stu-id="808e8-118">The specified function is not an exported function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="808e8-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="808e8-119">Remarks</span></span>  
 <span data-ttu-id="808e8-120">このメソッドにより、CLR が読み込まれますが、初期化されていません。</span><span class="sxs-lookup"><span data-stu-id="808e8-120">This method causes the CLR to be loaded but not initialized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="808e8-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="808e8-121">Requirements</span></span>  
 <span data-ttu-id="808e8-122">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="808e8-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="808e8-123">**ヘッダー:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="808e8-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="808e8-124">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="808e8-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="808e8-125">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="808e8-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="808e8-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="808e8-126">See also</span></span>

- [<span data-ttu-id="808e8-127">ICLRRuntimeInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="808e8-127">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="808e8-128">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="808e8-128">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="808e8-129">ホスティング</span><span class="sxs-lookup"><span data-stu-id="808e8-129">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
