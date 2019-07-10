---
title: ICLRRuntimeInfo::GetDefaultStartupFlags メソッド
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetDefaultStartupFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetDefaultStartupFlags
helpviewer_keywords:
- ICLRRuntimeInfo::GetDefaultStartupFlags method [.NET Framework hosting]
- GetDefaultStartupFlags method [.NET Framework hosting]
ms.assetid: 35c2173e-3b0b-4b2a-950d-e0a01c6df052
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aeb4c9935d5e9e4063497dd56276edfe6e62752a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67765586"
---
# <a name="iclrruntimeinfogetdefaultstartupflags-method"></a><span data-ttu-id="42590-102">ICLRRuntimeInfo::GetDefaultStartupFlags メソッド</span><span class="sxs-lookup"><span data-stu-id="42590-102">ICLRRuntimeInfo::GetDefaultStartupFlags Method</span></span>
<span data-ttu-id="42590-103">スタートアップ フラグとランタイムの起動に使用されるホスト構成ファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="42590-103">Gets the startup flags and host configuration file that will be used to start the runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42590-104">構文</span><span class="sxs-lookup"><span data-stu-id="42590-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDefaultStartupFlags(  
     [out]  DWORD *pdwStartupFlags,  
     [out, size_is(*pcchHostConfigFile)] LPWSTR pwzHostConfigFile,  
     [in, out]  DWORD *pcchHostConfigFile);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42590-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="42590-105">Parameters</span></span>  
 `pdwStartupFlags`  
 <span data-ttu-id="42590-106">[out]現在設定されているホストのスタートアップ フラグへのポインター。</span><span class="sxs-lookup"><span data-stu-id="42590-106">[out] A pointer to the host startup flags that are currently set.</span></span>  
  
 `pwzHostConfigFile`  
 <span data-ttu-id="42590-107">[out]現在のホスト構成ファイルのディレクトリ パスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="42590-107">[out] A pointer to the directory path of the current host configuration file.</span></span>  
  
 `pcchHostConfigFile`  
 <span data-ttu-id="42590-108">[入力、出力]入力のサイズ`pwzHostConfigFile`、バッファー オーバーランを回避します。</span><span class="sxs-lookup"><span data-stu-id="42590-108">[in, out] On input, the size of `pwzHostConfigFile`, to avoid buffer overruns.</span></span> <span data-ttu-id="42590-109">場合`pwzHostConfigFile`は null を返しますの必要なサイズ`pwzHostConfigFile`の事前割り当て。</span><span class="sxs-lookup"><span data-stu-id="42590-109">If `pwzHostConfigFile` is null, the method returns the required size of `pwzHostConfigFile` for pre-allocation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="42590-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="42590-110">Return Value</span></span>  
 <span data-ttu-id="42590-111">このメソッドは、次の特定の HRESULT を返します。 メソッドの失敗を示す HRESULT エラーとします。</span><span class="sxs-lookup"><span data-stu-id="42590-111">This method returns the following specific HRESULT as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="42590-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="42590-112">HRESULT</span></span>|<span data-ttu-id="42590-113">説明</span><span class="sxs-lookup"><span data-stu-id="42590-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="42590-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="42590-114">S_OK</span></span>|<span data-ttu-id="42590-115">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="42590-115">The method completed successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="42590-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="42590-116">Remarks</span></span>  
 <span data-ttu-id="42590-117">このメソッドは、既定のフラグ値を返します (`STARTUP_CONCURRENT_GC`と`NULL`)、または以前の呼び出しで指定された値、 [iclrruntimeinfo::setdefaultstartupflags メソッド](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-setdefaultstartupflags-method.md)、またはのいずれかによって設定された値、 `CorBind*`メソッドのこのランタイムにバインドされている場合。</span><span class="sxs-lookup"><span data-stu-id="42590-117">This method returns the default flag values (`STARTUP_CONCURRENT_GC` and `NULL`), or the values provided by a previous call to the [ICLRRuntimeInfo::SetDefaultStartupFlags method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-setdefaultstartupflags-method.md), or the values set by any of the `CorBind*` methods if they are bound to this runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42590-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="42590-118">Requirements</span></span>  
 <span data-ttu-id="42590-119">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="42590-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42590-120">**ヘッダー:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="42590-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="42590-121">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="42590-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="42590-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42590-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42590-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="42590-123">See also</span></span>

- [<span data-ttu-id="42590-124">ICLRRuntimeInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="42590-124">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="42590-125">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="42590-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="42590-126">ホスティング</span><span class="sxs-lookup"><span data-stu-id="42590-126">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
