---
title: GetVersionFromProcess 関数
ms.date: 03/30/2017
api_name:
- GetVersionFromProcess
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetVersionFromProcess
helpviewer_keywords:
- GetVersionFromProcess function [.NET Framework hosting]
ms.assetid: a9f7f824-64a1-408d-8607-91c7f19d21fe
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3055ac73f15329015f532f42c1f922eab38828cb
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490306"
---
# <a name="getversionfromprocess-function"></a><span data-ttu-id="f7207-102">GetVersionFromProcess 関数</span><span class="sxs-lookup"><span data-stu-id="f7207-102">GetVersionFromProcess Function</span></span>
<span data-ttu-id="f7207-103">指定されたプロセスのハンドルに関連付けられている共通言語ランタイム (CLR) のバージョン番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="f7207-103">Gets the version number of the common language runtime (CLR) that is associated with the specified process handle.</span></span>  
  
 <span data-ttu-id="f7207-104">この関数は、.NET Framework 4 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="f7207-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7207-105">構文</span><span class="sxs-lookup"><span data-stu-id="f7207-105">Syntax</span></span>  
  
```  
HRESULT GetVersionFromProcess (  
    [in]  HANDLE  hProcess,   
    [out] LPWSTR  pVersion,   
    [in]  DWORD   cchBuffer,   
    [out] DWORD  *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7207-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f7207-106">Parameters</span></span>  
 `hProcess`  
 <span data-ttu-id="f7207-107">[in]プロセスへのハンドル。</span><span class="sxs-lookup"><span data-stu-id="f7207-107">[in] A handle to a process.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="f7207-108">[out]正常に終了メソッドのバージョン番号の文字列を格納するバッファー。</span><span class="sxs-lookup"><span data-stu-id="f7207-108">[out] A buffer that contains the version number string upon successful completion of the method.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="f7207-109">[in]バージョンのバッファーの長さ。</span><span class="sxs-lookup"><span data-stu-id="f7207-109">[in] The length of the version buffer.</span></span>  
  
 `pdwLength`  
 <span data-ttu-id="f7207-110">[out]バージョン番号の文字列の長さへのポインター。</span><span class="sxs-lookup"><span data-stu-id="f7207-110">[out] A pointer to the length of the version number string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f7207-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="f7207-111">Return Value</span></span>  
 <span data-ttu-id="f7207-112">このメソッドは、次の値だけでなく、WinError.h で定義されている標準のコンポーネント オブジェクト モデル (COM) エラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="f7207-112">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="f7207-113">リターン コード</span><span class="sxs-lookup"><span data-stu-id="f7207-113">Return code</span></span>|<span data-ttu-id="f7207-114">説明</span><span class="sxs-lookup"><span data-stu-id="f7207-114">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="f7207-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="f7207-115">S_OK</span></span>|<span data-ttu-id="f7207-116">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="f7207-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="f7207-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="f7207-117">E_INVALIDARG</span></span>|<span data-ttu-id="f7207-118">`pVersion` null と`cchBuffer`が null でないまたはその逆です。</span><span class="sxs-lookup"><span data-stu-id="f7207-118">`pVersion` is null and `cchBuffer` is not null, or vice versa.</span></span><br /><br /> <span data-ttu-id="f7207-119">- または -</span><span class="sxs-lookup"><span data-stu-id="f7207-119">-or-</span></span><br /><br /> <span data-ttu-id="f7207-120">`hProcess` プロセスに有効なハンドルではありません。</span><span class="sxs-lookup"><span data-stu-id="f7207-120">`hProcess` is not a valid handle to a process.</span></span><br /><br /> <span data-ttu-id="f7207-121">- または -</span><span class="sxs-lookup"><span data-stu-id="f7207-121">-or-</span></span><br /><br /> <span data-ttu-id="f7207-122">CLR は読み込まれません。</span><span class="sxs-lookup"><span data-stu-id="f7207-122">The CLR is not loaded.</span></span>|  
|<span data-ttu-id="f7207-123">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="f7207-123">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="f7207-124">`cchBuffer` null か、バージョン文字列の長さよりも小さい。</span><span class="sxs-lookup"><span data-stu-id="f7207-124">`cchBuffer` is null or less than the length of the version string.</span></span>|  
|<span data-ttu-id="f7207-125">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="f7207-125">E_NOTIMPL</span></span>|<span data-ttu-id="f7207-126">このメソッドは、Microsoft Windows 95、Microsoft Windows 98、または Microsoft Windows Millennium Edition オペレーティング システムでご利用いただけません。</span><span class="sxs-lookup"><span data-stu-id="f7207-126">This method is not available on the Microsoft Windows 95, Microsoft Windows 98, or Microsoft Windows Millennium Edition operating system.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f7207-127">必要条件</span><span class="sxs-lookup"><span data-stu-id="f7207-127">Requirements</span></span>  
 <span data-ttu-id="f7207-128">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7207-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7207-129">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f7207-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f7207-130">**ライブラリ:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f7207-130">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f7207-131">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7207-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7207-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="f7207-132">See also</span></span>

- [<span data-ttu-id="f7207-133">GetRequestedRuntimeInfo 関数</span><span class="sxs-lookup"><span data-stu-id="f7207-133">GetRequestedRuntimeInfo Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)
- [<span data-ttu-id="f7207-134">GetRequestedRuntimeVersion 関数</span><span class="sxs-lookup"><span data-stu-id="f7207-134">GetRequestedRuntimeVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)
- [<span data-ttu-id="f7207-135">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="f7207-135">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
