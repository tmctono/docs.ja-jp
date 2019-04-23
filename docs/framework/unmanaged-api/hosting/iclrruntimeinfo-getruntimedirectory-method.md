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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5c09f57ad805b4ba17b4bdafd3ced533199277a0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59196685"
---
# <a name="iclrruntimeinfogetruntimedirectory-method"></a><span data-ttu-id="f6acb-102">ICLRRuntimeInfo::GetRuntimeDirectory メソッド</span><span class="sxs-lookup"><span data-stu-id="f6acb-102">ICLRRuntimeInfo::GetRuntimeDirectory Method</span></span>
<span data-ttu-id="f6acb-103">このインターフェイスに関連付けられている共通言語ランタイム (CLR) のインストール ディレクトリを取得します。</span><span class="sxs-lookup"><span data-stu-id="f6acb-103">Gets the installation directory of the common language runtime (CLR) associated with this interface.</span></span>  
  
 <span data-ttu-id="f6acb-104">このメソッドは、 [GetCORSystemDirectory](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md) .NET Framework バージョン 2.0、3.0、および 3.5 で提供される関数。</span><span class="sxs-lookup"><span data-stu-id="f6acb-104">This method supersedes the [GetCORSystemDirectory](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md) function provided in the .NET Framework versions 2.0, 3.0, and 3.5.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6acb-105">構文</span><span class="sxs-lookup"><span data-stu-id="f6acb-105">Syntax</span></span>  
  
```  
HRESULT GetRuntimeDirectory(  
[out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
[in, out]  DWORD *pcchBuffer);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f6acb-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f6acb-106">Parameters</span></span>  
 `pwzBuffer`  
 <span data-ttu-id="f6acb-107">[out]CLR のインストール ディレクトリを返します。</span><span class="sxs-lookup"><span data-stu-id="f6acb-107">[out] Returns the CLR installation directory.</span></span> <span data-ttu-id="f6acb-108">インストール パスは、完全修飾;たとえば、"c:\windows\microsoft.net\framework\v1.0.3705\\"。</span><span class="sxs-lookup"><span data-stu-id="f6acb-108">The installation path is fully qualified; for example, "c:\windows\microsoft.net\framework\v1.0.3705\\".</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="f6acb-109">[入力、出力]サイズを示す`pwzBuffer`バッファー オーバーランを回避します。</span><span class="sxs-lookup"><span data-stu-id="f6acb-109">[in, out] Specifies the size of `pwzBuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="f6acb-110">場合`pwzBuffer`が null、`pchBuffer`の必要なサイズを返します`pwzBuffer`します。</span><span class="sxs-lookup"><span data-stu-id="f6acb-110">If `pwzBuffer` is null, `pchBuffer` returns the required size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f6acb-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="f6acb-111">Return Value</span></span>  
 <span data-ttu-id="f6acb-112">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="f6acb-112">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="f6acb-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f6acb-113">HRESULT</span></span>|<span data-ttu-id="f6acb-114">説明</span><span class="sxs-lookup"><span data-stu-id="f6acb-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f6acb-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="f6acb-115">S_OK</span></span>|<span data-ttu-id="f6acb-116">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="f6acb-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="f6acb-117">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="f6acb-117">E_POINTER</span></span>|<span data-ttu-id="f6acb-118">`pwzBuffer` または `pchBuffer` が null です。</span><span class="sxs-lookup"><span data-stu-id="f6acb-118">`pwzBuffer` or `pchBuffer` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f6acb-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="f6acb-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6acb-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="f6acb-120">Requirements</span></span>  
 <span data-ttu-id="f6acb-121">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6acb-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6acb-122">**ヘッダー:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="f6acb-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="f6acb-123">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="f6acb-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f6acb-124">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6acb-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6acb-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="f6acb-125">See also</span></span>

- [<span data-ttu-id="f6acb-126">ICLRRuntimeInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f6acb-126">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="f6acb-127">ホスティング</span><span class="sxs-lookup"><span data-stu-id="f6acb-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
