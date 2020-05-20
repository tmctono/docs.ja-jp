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
ms.openlocfilehash: 8513787f48ae89632816face386bbcda20555dac
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703885"
---
# <a name="iclrruntimeinfogetdefaultstartupflags-method"></a><span data-ttu-id="40bfa-102">ICLRRuntimeInfo::GetDefaultStartupFlags メソッド</span><span class="sxs-lookup"><span data-stu-id="40bfa-102">ICLRRuntimeInfo::GetDefaultStartupFlags Method</span></span>
<span data-ttu-id="40bfa-103">ランタイムを開始するために使用されるスタートアップフラグとホスト構成ファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="40bfa-103">Gets the startup flags and host configuration file that will be used to start the runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40bfa-104">構文</span><span class="sxs-lookup"><span data-stu-id="40bfa-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDefaultStartupFlags(  
     [out]  DWORD *pdwStartupFlags,  
     [out, size_is(*pcchHostConfigFile)] LPWSTR pwzHostConfigFile,  
     [in, out]  DWORD *pcchHostConfigFile);  
```  
  
## <a name="parameters"></a><span data-ttu-id="40bfa-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="40bfa-105">Parameters</span></span>  
 `pdwStartupFlags`  
 <span data-ttu-id="40bfa-106">入出力現在設定されているホストのスタートアップフラグへのポインター。</span><span class="sxs-lookup"><span data-stu-id="40bfa-106">[out] A pointer to the host startup flags that are currently set.</span></span>  
  
 `pwzHostConfigFile`  
 <span data-ttu-id="40bfa-107">入出力現在のホスト構成ファイルのディレクトリパスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="40bfa-107">[out] A pointer to the directory path of the current host configuration file.</span></span>  
  
 `pcchHostConfigFile`  
 <span data-ttu-id="40bfa-108">[入力、出力]入力時には、 `pwzHostConfigFile` バッファーオーバーランを回避するためののサイズ。</span><span class="sxs-lookup"><span data-stu-id="40bfa-108">[in, out] On input, the size of `pwzHostConfigFile`, to avoid buffer overruns.</span></span> <span data-ttu-id="40bfa-109">`pwzHostConfigFile`が null の場合、メソッドは、 `pwzHostConfigFile` 事前割り当てのために必要なサイズを返します。</span><span class="sxs-lookup"><span data-stu-id="40bfa-109">If `pwzHostConfigFile` is null, the method returns the required size of `pwzHostConfigFile` for pre-allocation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="40bfa-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="40bfa-110">Return Value</span></span>  
 <span data-ttu-id="40bfa-111">このメソッドは、次の特定の HRESULT と、メソッドエラーを示す HRESULT エラーを返します。</span><span class="sxs-lookup"><span data-stu-id="40bfa-111">This method returns the following specific HRESULT as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="40bfa-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="40bfa-112">HRESULT</span></span>|<span data-ttu-id="40bfa-113">説明</span><span class="sxs-lookup"><span data-stu-id="40bfa-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="40bfa-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="40bfa-114">S_OK</span></span>|<span data-ttu-id="40bfa-115">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="40bfa-115">The method completed successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40bfa-116">解説</span><span class="sxs-lookup"><span data-stu-id="40bfa-116">Remarks</span></span>  
 <span data-ttu-id="40bfa-117">このメソッドは、既定のフラグ値 ( `STARTUP_CONCURRENT_GC` および `NULL` )、または[ICLRRuntimeInfo:: SetDefaultStartupFlags メソッド](iclrruntimeinfo-setdefaultstartupflags-method.md)の以前の呼び出しによって提供された値、または `CorBind*` メソッドがこのランタイムにバインドされている場合は、いずれかのメソッドによって設定された値を返します。</span><span class="sxs-lookup"><span data-stu-id="40bfa-117">This method returns the default flag values (`STARTUP_CONCURRENT_GC` and `NULL`), or the values provided by a previous call to the [ICLRRuntimeInfo::SetDefaultStartupFlags method](iclrruntimeinfo-setdefaultstartupflags-method.md), or the values set by any of the `CorBind*` methods if they are bound to this runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40bfa-118">要件</span><span class="sxs-lookup"><span data-stu-id="40bfa-118">Requirements</span></span>  
 <span data-ttu-id="40bfa-119">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40bfa-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40bfa-120">**ヘッダー:** メタホスト .h</span><span class="sxs-lookup"><span data-stu-id="40bfa-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="40bfa-121">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="40bfa-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="40bfa-122">**.NET Framework のバージョン:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40bfa-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40bfa-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="40bfa-123">See also</span></span>

- [<span data-ttu-id="40bfa-124">ICLRRuntimeInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="40bfa-124">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="40bfa-125">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="40bfa-125">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="40bfa-126">ホスティング</span><span class="sxs-lookup"><span data-stu-id="40bfa-126">Hosting</span></span>](index.md)
