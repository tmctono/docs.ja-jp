---
title: ICLRRuntimeInfo::GetRuntimeDirectory メソッド
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetRuntimeDirectory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetRuntimeDirectory
helpviewer_keywords:
- GetRuntimeDirectory method [.NET Framework hosting]
- ICLRRuntimeInfo::GetRuntimeDirectory method [.NET Framework hosting]
ms.assetid: 4401546e-4d48-453f-a1fb-b2ebda54df5c
topic_type:
- apiref
ms.openlocfilehash: b0a2e5f259fe1ee566f9cc25152b2d2a1f740bea
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120336"
---
# <a name="iclrruntimeinfogetruntimedirectory-method"></a><span data-ttu-id="3b502-102">ICLRRuntimeInfo::GetRuntimeDirectory メソッド</span><span class="sxs-lookup"><span data-stu-id="3b502-102">ICLRRuntimeInfo::GetRuntimeDirectory Method</span></span>
<span data-ttu-id="3b502-103">このインターフェイスに関連付けられている共通言語ランタイム (CLR) のインストールディレクトリを取得します。</span><span class="sxs-lookup"><span data-stu-id="3b502-103">Gets the installation directory of the common language runtime (CLR) associated with this interface.</span></span>  
  
 <span data-ttu-id="3b502-104">このメソッドは、.NET Framework バージョン2.0、3.0、および3.5 で提供される[Getcorsystemdirectory](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md)関数よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="3b502-104">This method supersedes the [GetCORSystemDirectory](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md) function provided in the .NET Framework versions 2.0, 3.0, and 3.5.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b502-105">構文</span><span class="sxs-lookup"><span data-stu-id="3b502-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRuntimeDirectory(  
[out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
[in, out]  DWORD *pcchBuffer);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b502-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3b502-106">Parameters</span></span>  
 `pwzBuffer`  
 <span data-ttu-id="3b502-107">入出力CLR インストールディレクトリを返します。</span><span class="sxs-lookup"><span data-stu-id="3b502-107">[out] Returns the CLR installation directory.</span></span> <span data-ttu-id="3b502-108">インストールパスは完全修飾されています。たとえば、"c:\windows\microsoft.net\framework\v1.0.3705\\" のようになります。</span><span class="sxs-lookup"><span data-stu-id="3b502-108">The installation path is fully qualified; for example, "c:\windows\microsoft.net\framework\v1.0.3705\\".</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="3b502-109">[入力、出力]バッファーオーバーランを回避するための `pwzBuffer` のサイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="3b502-109">[in, out] Specifies the size of `pwzBuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="3b502-110">`pwzBuffer` が null の場合、`pchBuffer` は `pwzBuffer`の必要なサイズを返します。</span><span class="sxs-lookup"><span data-stu-id="3b502-110">If `pwzBuffer` is null, `pchBuffer` returns the required size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3b502-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="3b502-111">Return Value</span></span>  
 <span data-ttu-id="3b502-112">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="3b502-112">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="3b502-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3b502-113">HRESULT</span></span>|<span data-ttu-id="3b502-114">説明</span><span class="sxs-lookup"><span data-stu-id="3b502-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3b502-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="3b502-115">S_OK</span></span>|<span data-ttu-id="3b502-116">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="3b502-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="3b502-117">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="3b502-117">E_POINTER</span></span>|<span data-ttu-id="3b502-118">`pwzBuffer` または `pchBuffer` が null です。</span><span class="sxs-lookup"><span data-stu-id="3b502-118">`pwzBuffer` or `pchBuffer` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3b502-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="3b502-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b502-120">［要件］</span><span class="sxs-lookup"><span data-stu-id="3b502-120">Requirements</span></span>  
 <span data-ttu-id="3b502-121">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b502-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b502-122">**ヘッダー:** メタホスト .h</span><span class="sxs-lookup"><span data-stu-id="3b502-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="3b502-123">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="3b502-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3b502-124">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b502-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b502-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="3b502-125">See also</span></span>

- [<span data-ttu-id="3b502-126">ICLRRuntimeInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3b502-126">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="3b502-127">ホスティング</span><span class="sxs-lookup"><span data-stu-id="3b502-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
