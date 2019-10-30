---
title: ICLRRuntimeInfo::GetVersionString メソッド
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetVersionString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetVersionString
helpviewer_keywords:
- ICLRRuntimeInfo::GetVersionString method [.NET Framework hosting]
- GetVersionString method, ICLRRuntimeInfo interface [.NET Framework hosting]
ms.assetid: 98b097ef-2276-4dd9-8551-b03c972e8179
topic_type:
- apiref
ms.openlocfilehash: 0b6ac83cdd0c88e87fdfd552c76c906a334f8928
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120301"
---
# <a name="iclrruntimeinfogetversionstring-method"></a><span data-ttu-id="0a7f0-102">ICLRRuntimeInfo::GetVersionString メソッド</span><span class="sxs-lookup"><span data-stu-id="0a7f0-102">ICLRRuntimeInfo::GetVersionString Method</span></span>
<span data-ttu-id="0a7f0-103">指定した[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)インターフェイスに関連付けられている共通言語ランタイム (CLR) のバージョン情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="0a7f0-103">Gets common language runtime (CLR) version information associated with a given [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="0a7f0-104">このメソッドは、次の関数を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="0a7f0-104">This method supersedes the following functions:</span></span>  
  
- [<span data-ttu-id="0a7f0-105">GetRequestedRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="0a7f0-105">GetRequestedRuntimeInfo</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)  
  
- [<span data-ttu-id="0a7f0-106">GetRequestedRuntimeVersion</span><span class="sxs-lookup"><span data-stu-id="0a7f0-106">GetRequestedRuntimeVersion</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)  
  
## <a name="syntax"></a><span data-ttu-id="0a7f0-107">構文</span><span class="sxs-lookup"><span data-stu-id="0a7f0-107">Syntax</span></span>  
  
```cpp  
HRESULT GetVersionString(  
    [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
    [in, out]  DWORD *pcchBuffer);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0a7f0-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0a7f0-108">Parameters</span></span>  
 `pwzBuffer`  
 <span data-ttu-id="0a7f0-109">入出力.NET Framework のコンパイルバージョンを "v*A*" という形式で指定します。*B*[.*X*] "</span><span class="sxs-lookup"><span data-stu-id="0a7f0-109">[out] The .NET Framework compilation version in the format "v*A*.*B*[.*X*]".</span></span> <span data-ttu-id="0a7f0-110">*A*、 *B*、および*X*は、メジャーバージョン、マイナーバージョン、およびビルド番号に対応する10進数です。</span><span class="sxs-lookup"><span data-stu-id="0a7f0-110">*A*, *B*, and *X* are decimal numbers that correspond to the major version, the minor version, and the build number.</span></span> <span data-ttu-id="0a7f0-111">*X*は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="0a7f0-111">*X* is optional.</span></span> <span data-ttu-id="0a7f0-112">*X*が存在しない場合、末尾のピリオドはありません。</span><span class="sxs-lookup"><span data-stu-id="0a7f0-112">If *X* is not present, there is no trailing period.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0a7f0-113">このパラメーターは、C:\Windows\Microsoft.NET\Framework. の下に表示される .NET Framework バージョンのディレクトリ名と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a7f0-113">This parameter must match the directory name for the .NET Framework version, as it appears under C:\Windows\Microsoft.NET\Framework.</span></span>  
  
 <span data-ttu-id="0a7f0-114">値の例としては、"v v1.0.3705"、"v 1.1.4322"、"v v2.0.50727"、および "v4.0" があります。*x*"。ここで*x*は、インストールされているビルド番号に依存します。</span><span class="sxs-lookup"><span data-stu-id="0a7f0-114">Example values are "v1.0.3705", "v1.1.4322", "v2.0.50727", and "v4.0.*x*", where *x* depends on the build number installed.</span></span> <span data-ttu-id="0a7f0-115">"V" プレフィックスが必須であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0a7f0-115">Note that the "v" prefix is mandatory.</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="0a7f0-116">[入力、出力]バッファーオーバーランを回避するための `pwzBuffer` のサイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="0a7f0-116">[in, out] Specifies the size of `pwzBuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="0a7f0-117">`pwzBuffer` が `null`場合、`pchBuffer` は、事前割り当てを許可するために必要なサイズの `pwzBuffer` を返します。</span><span class="sxs-lookup"><span data-stu-id="0a7f0-117">If `pwzBuffer` is `null`, `pchBuffer` returns the required size of `pwzBuffer` to allow preallocation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0a7f0-118">戻り値</span><span class="sxs-lookup"><span data-stu-id="0a7f0-118">Return Value</span></span>  
 <span data-ttu-id="0a7f0-119">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="0a7f0-119">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="0a7f0-120">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0a7f0-120">HRESULT</span></span>|<span data-ttu-id="0a7f0-121">説明</span><span class="sxs-lookup"><span data-stu-id="0a7f0-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0a7f0-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="0a7f0-122">S_OK</span></span>|<span data-ttu-id="0a7f0-123">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="0a7f0-123">The method completed successfully.</span></span>|  
|<span data-ttu-id="0a7f0-124">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="0a7f0-124">E_POINTER</span></span>|<span data-ttu-id="0a7f0-125">`pwzBuffer` または `pchBuffer` が null です。</span><span class="sxs-lookup"><span data-stu-id="0a7f0-125">`pwzBuffer` or `pchBuffer` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0a7f0-126">［要件］</span><span class="sxs-lookup"><span data-stu-id="0a7f0-126">Requirements</span></span>  
 <span data-ttu-id="0a7f0-127">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a7f0-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a7f0-128">**ヘッダー:** メタホスト .h</span><span class="sxs-lookup"><span data-stu-id="0a7f0-128">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="0a7f0-129">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="0a7f0-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0a7f0-130">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a7f0-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a7f0-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="0a7f0-131">See also</span></span>

- [<span data-ttu-id="0a7f0-132">ICLRRuntimeInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0a7f0-132">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="0a7f0-133">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0a7f0-133">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="0a7f0-134">.NET Framework 4 および 4.5 で追加された CLR ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0a7f0-134">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [<span data-ttu-id="0a7f0-135">ホスティング</span><span class="sxs-lookup"><span data-stu-id="0a7f0-135">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
