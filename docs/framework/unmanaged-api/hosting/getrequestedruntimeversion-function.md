---
title: GetRequestedRuntimeVersion 関数
ms.date: 03/30/2017
api_name:
- GetRequestedRuntimeVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetRequestedRuntimeVersion
helpviewer_keywords:
- GetRequestedRuntimeVersion function [.NET Framework hosting]
ms.assetid: 82f596a4-483d-4509-b0c5-a84c53c3da1b
topic_type:
- apiref
ms.openlocfilehash: 6be0bc5d08f612dcb8ed7d256711e0c4367b9274
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178138"
---
# <a name="getrequestedruntimeversion-function"></a><span data-ttu-id="df99d-102">GetRequestedRuntimeVersion 関数</span><span class="sxs-lookup"><span data-stu-id="df99d-102">GetRequestedRuntimeVersion Function</span></span>
<span data-ttu-id="df99d-103">指定したアプリケーションによって要求された共通言語ランタイム (CLR) のバージョン番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="df99d-103">Gets the version number of the common language runtime (CLR) requested by the specified application.</span></span> <span data-ttu-id="df99d-104">そのバージョンがインストールされていない場合は、要求されるバージョンより前にインストールされた最も新しいバージョンを取得します。</span><span class="sxs-lookup"><span data-stu-id="df99d-104">If that version is not installed, gets the most recent version that is installed before the requested version.</span></span>  
  
 <span data-ttu-id="df99d-105">この関数は、.NET Framework 4 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="df99d-105">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df99d-106">構文</span><span class="sxs-lookup"><span data-stu-id="df99d-106">Syntax</span></span>  
  
```cpp  
HRESULT GetRequestedRuntimeVersion (  
    [in]  LPWSTR  pExe,
    [out] LPWSTR  pVersion,
    [in]  DWORD   cchBuffer,
    [out] DWORD  *pdwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df99d-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="df99d-107">Parameters</span></span>  
 `pExe`  
 <span data-ttu-id="df99d-108">[in]アプリケーションの名前。</span><span class="sxs-lookup"><span data-stu-id="df99d-108">[in] The name of the application.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="df99d-109">[アウト]正常終了した場合に、バージョン番号文字列を格納するバッファー。</span><span class="sxs-lookup"><span data-stu-id="df99d-109">[out] A buffer that contains the version number string upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="df99d-110">[in]バージョン バッファーの長さ。</span><span class="sxs-lookup"><span data-stu-id="df99d-110">[in] The length of the version buffer.</span></span>  
  
 `pdwLength`  
 <span data-ttu-id="df99d-111">[アウト]バージョン番号文字列の長さへのポインター。</span><span class="sxs-lookup"><span data-stu-id="df99d-111">[out] A pointer to the length of the version number string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="df99d-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="df99d-112">Return Value</span></span>  
 <span data-ttu-id="df99d-113">このメソッドは、WinError.h で定義されている次の値に加えて、標準のコンポーネント オブジェクト モデル (COM) エラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="df99d-113">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="df99d-114">リターン コード</span><span class="sxs-lookup"><span data-stu-id="df99d-114">Return code</span></span>|<span data-ttu-id="df99d-115">説明</span><span class="sxs-lookup"><span data-stu-id="df99d-115">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="df99d-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="df99d-116">S_OK</span></span>|<span data-ttu-id="df99d-117">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="df99d-117">The method completed successfully.</span></span>|  
|<span data-ttu-id="df99d-118">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="df99d-118">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="df99d-119">バージョン バッファーのサイズが、バージョン文字列を格納するのに十分ではありません。</span><span class="sxs-lookup"><span data-stu-id="df99d-119">The version buffer is not large enough to store the version string.</span></span>|  
|<span data-ttu-id="df99d-120">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="df99d-120">E_POINTER</span></span>|<span data-ttu-id="df99d-121">`pdwLength` が null です。</span><span class="sxs-lookup"><span data-stu-id="df99d-121">`pdwLength` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="df99d-122">必要条件</span><span class="sxs-lookup"><span data-stu-id="df99d-122">Requirements</span></span>  
 <span data-ttu-id="df99d-123">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df99d-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df99d-124">**ヘッダー:** msCorEE.h</span><span class="sxs-lookup"><span data-stu-id="df99d-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="df99d-125">**ライブラリ:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="df99d-125">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="df99d-126">**.NET Framework のバージョン:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df99d-126">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df99d-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="df99d-127">See also</span></span>

- [<span data-ttu-id="df99d-128">GetRequestedRuntimeInfo 関数</span><span class="sxs-lookup"><span data-stu-id="df99d-128">GetRequestedRuntimeInfo Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)
- [<span data-ttu-id="df99d-129">GetVersionFromProcess 関数</span><span class="sxs-lookup"><span data-stu-id="df99d-129">GetVersionFromProcess Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)
- [<span data-ttu-id="df99d-130">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="df99d-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
